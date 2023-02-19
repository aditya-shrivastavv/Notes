
# React Router Dom

## Installation

```bash
npm install react-router-dom@6
```

### Features

- `BrowserRouter`
  - wraps the parent component so that react router can work in it and it's children.

- `Routes`
  - contains multiple `Route` components.

- `Route`
  - must be inside of a `Routes` component
  - two main props:
    - `path`
      - the path to match
    - `element`
      - the component to render when the path matches

- `Link`
  - substitutes the `a` tag
  - main props include `to` the path to navigate to
  - when we do `/something` it will set primary path to `/something` but, if we want to do nested route then we should do `something` then, `something` will add to the primary path.

- `NavLink`
  - Similar to `Link` but it add an `active` class when the path matches thus allowing for styling
  - specially meant for navigation links
  - props includes `style`. we can pass a function to the style, then destructure the `isActive` prop and the we can apply objectified style to the `Link` component on the basis of it.

---

- `useNavigate`
  - a hook provided by react router dom, initiate it in the component `const navigate = useNavigate()` and then use it to navigate to a path `navigate('/path')`
  - it adds path programmatically, means on an event
  - `navigate(-1)` will go back to the previous page.
  - see more at [useNavigate](https://reactrouter.com/en/6.8.1/hooks/use-navigate)

- `<Outlet />`
  - // TODO - give the space for rendering child components ?

---

### Others

> configuring a default route

- in the paths add a `path="/"` and then add a `element` prop with the component to render when no match is found.
  
> configuring a no match route

- in the paths add a `path="*"` and then add a `element` prop with the component to render when no match is found.

> ### Nested Routes

- `/path` and `path` are different, `/path` will match the path exactly and `path` will match the path partially.
- paths can be nested just like comman html elements in `<Route>` tag. the react-router will automatically match the paths for nested components.
