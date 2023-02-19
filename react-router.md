# React Router Dom

## Installation

```bash
npm install react-router-dom@6
```

### Features

- `BrowserRouter` --component

  - wraps the parent component so that react router can work in it and it's children.

  ```jsx
  <BrowserRouter>// will be available to all the children</BrowserRouter>
  ```

- `Routes` --component

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

  - `INDEX ROUTE`

    - if we want a child route to be rendered at parent level then we can use index route

  ```jsx
  <Route>
    <Route path="products" element={<Products />}>
      // will be rendered at /products
      <Route index element={<FeaturedProducts />} />

      <Route path="featured" element={<FeaturedProducts />} />
      <Route path="new" element={<NewProducts />} />
    </Route>
  ```

- `Route` --component

  - must be inside of a `Routes` component
  - two main props: `path` - the path to match and `element` - the component to render when the path matches
  - can be nested inside of another `Route` component to create nested routes

  ```jsx
  <Route path="/" element={<Home />} />
  <Route path="/about" element={<About />} />
  ```

- `Link` --component

  - substitutes for `a` tag. `a` tag reloads the page but `Link` doesn't.
  - it's main props include `to` the path to navigate to.

  ```jsx
  <Link to="/about">About</Link>
  <Link to="about">About</Link>
  ```

  - both are different things as the first one will match the path exactly from the root and the second one will add the path to the current path.

- `NavLink` --component

  - Similar to `Link` but it add an `active` class when the path matches thus allowing for styling
  - specially meant for navigation links in the navigation bar.
  - > props includes `style`. we can pass a function to the style, then destructure the `isActive` prop and the we can apply objectified style to the `Link` component on the basis of it.

- `useNavigate` --hook

  - a hook provided by react router dom to do programmatic routing, first initiate it in the component and then use it's instance to navigate to a path.

  ```jsx
  const navigate = useNavigate();

  const handleClick = () => {
    navigate("/path");
  };
  ```

  - > `navigate(-1)` will go back to the previous page.
  - see more at [useNavigate](https://reactrouter.com/en/6.8.1/hooks/use-navigate)

- `Outlet` --component

  - // TODO - give the space for rendering child components ?

---

### Tips, Tricks and Gotchas

> configuring a default route

- in the paths add a `path="/"` and then add a `element` prop with the component to render when no match is found.

> configuring a no match route

- in the paths add a `path="*"` and then add a `element` prop with the component to render when no match is found.

---
