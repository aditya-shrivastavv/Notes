# React Router Dom

- [React Router Dom](#react-router-dom)
  - [Installation](#installation)
  - [Features](#features)
    - [`BrowserRouter` --component](#browserrouter---component)
    - [`Routes` --component](#routes---component)
    - [`Route` --component](#route---component)
      - [`INDEX ROUTE`](#index-route)
    - [`Link` --component](#link---component)
    - [`NavLink` --component](#navlink---component)
    - [`Outlet` --component](#outlet---component)
    - [`React.lazy` --function](#reactlazy---function)
    - [`useNavigate` --hook](#usenavigate---hook)
    - [`useParams` --hook](#useparams---hook)
    - [`useSearchParams` --hook](#usesearchparams---hook)
  - [Tips, Tricks and Gotchas](#tips-tricks-and-gotchas)
    - [configuring a default route](#configuring-a-default-route)
    - [configuring a no match route](#configuring-a-no-match-route)
    - [dynamic routes](#dynamic-routes)

## Installation

```bash
npm install react-router-dom@6
```

## Features

### `BrowserRouter` --component

- wraps the parent component so that react router can work in it and it's children.

```jsx
<BrowserRouter>// will be available to all the children</BrowserRouter>
```

### `Routes` --component

- contains multiple `Route` components.

```jsx
<Routes>
  // Route 1
  <Route path="/" element={<Home />} />
  // Route 2
  <Route path="/about" element={<About />} />
  // Route . . .
</Routes>
```

### `Route` --component

- must be inside of a `Routes` component
- two main props: `path` - the path to match and `element` - the component to render when the path matches
- can be nested inside of another `Route` component to create nested routes

```jsx
<Route path="/" element={<Home />} />
<Route path="/about" element={<About />} />
```

#### `INDEX ROUTE`

- if we want a child route to be rendered at parent url then we can use indexed route

```jsx
<Route>
  <Route path="products" element={<Products />}>
    // will be rendered at /products
    <Route index element={<FeaturedProducts />} />

    <Route path="featured" element={<FeaturedProducts />} />
    <Route path="new" element={<NewProducts />} />
  </Route>
```

### `Link` --component

- substitutes for `a` tag. `a` tag reloads the page but `Link` doesn't.
- it's main props include `to` the path to navigate to.

```jsx
<Link to="/about">About</Link>
<Link to="about">About</Link>
```

- both are different things as the first (absolute link) one will match the path exactly from the root and the second one (relative link)will add the path to the current path.

### `NavLink` --component

- Similar to `Link` but it add an `active` class when the path matches thus allowing for styling
- specially meant for navigation links in the navigation bar.

> props includes `style`. we can pass a function to the style, then destructure the `isActive` prop and the we can apply objectified style to the `Link` component on the basis of it.

### `Outlet` --component

- should be used in parent route elements to render their child route elements. This allows nested UI to show up when child routes are rendered. If the parent route matched exactly, it will render a child index route or nothing if there is no index route.

### `React.lazy` --function

- a function provided by react to lazy load components.

```jsx
import React from "react";
const lazyPage = React.lazy(() => import("./LazyPage"));
.
.
<Route path="about" element={
  <React.Suspense fallback="Loading . . . . ">
    <lazyPage />
  </React.Suspense>
}/>
```

- while a lazy component is loading, it needs a fallback component to show.

```jsx

```

### `useNavigate` --hook

- a hook provided by react router dom to do programmatic routing, first initiate it in the component and then use it's instance to navigate to a path.

```jsx
const navigate = useNavigate();

const handleClick = () => {
  navigate("/path");
};
```

> `navigate(-1)` will go back to the previous page.

- see more at [useNavigate](https://reactrouter.com/en/6.8.1/hooks/use-navigate)

### `useParams` --hook

- a hook provided by react router dom to get the params from the url.
- it returns an object with the params as key value pairs.

```jsx
const { id } = useParams();
```

### `useSearchParams` --hook

- a hook provided by react router dom to get and set the search params from the url.
- it works similar to `useState` hook but, it works with the search params of the url.

```jsx
const [searchParams, setSearchParams] = useSearchParams();
```

- `.get` is a method to first value associated to the given search parameter.
- `.getAll` is a method to get all the values associated to the given search parameter.

---

## Tips, Tricks and Gotchas

### configuring a default route

- in the paths add a `path="/"` and then add a `element` prop with the component to render when no match is found.

### configuring a no match route

- in the paths add a `path="*"` and then add a `element` prop with the component to render when no match is found.

### dynamic routes

- we can make a route dynamic by adding a `:` before the name of individual route.
- dynamic routes can be nested.

  ```jsx
  <Route path="/products/:id" element={<Product />} />
  <Route path="/products/relevent" element={<ReleventProduct />} />
  ```

- `:id` can be of any type, a string as well as a number
- react router tries to match a specific route first and then tries to match a dynamic route.
- for example - react router is smart enough to render `<ReleventProduct />` component when the path is `/products/relevent` and `<Product />` component when the path is `/products/1` or `/products/2` or `/products/3` etc.
