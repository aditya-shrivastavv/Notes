
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