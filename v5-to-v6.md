# v5 to v6

- v5's "Switch" component is deprecated, v6's "Routes" replaces it.
- The "Route" component now accepts an "element" prop instead of passing the component as children.
- v5's "exact" is deprecated. It is now the default route matching behavior in v6.
  - It is possible to use the old behavior by adding "/\*" to the end of the path.
- v6 route matching algorithm is "smarter", therefore there is no need to think about the order of routes with the same prefix. The most "suitable" route will be choosen.
- In v6, NavLink's "activeClassName" prop is deprecated in favor of "className", which now receives a function to determine the route state.
- v5's "Redirect" is deprecated in favor of v6's "Navigate".
  - The default behavior of "Navigate" is to push a route. It is possible to replace instead of push by using the "replace" prop.
- In v6, nested routes has to be wrapped by the "Routes" components, although it was not required to do so in v5.
- Because of the new "exact by default" route matching in v6, parent routes would have to use the "/\*" syntax if they use nested routes.
- In v6, nested routes "path" prop is now relative to the parent path, no need to specify the whole path as it was required in v5.
  - Same goes for the "Link" component - links are relative inside nested routes.
- v6's "Route" component now receives an optional "Route" components as children. The children are the nested routes of the parent route.
  - The main benefit of this pattern is that all the routes can be defined in one central place for better understanding the logic of the application instead of nested routes being hidden all over the place inside components.
  - When using this functionality, an "Outlet" component should be placed inside the parent route component to let react router know where in the parent route component the child route component should be rendered.
- v5's "useHistory" hook is now deprecated, v6 replacement is the "useNavigate" hook. Programmatically pushing/replacing a route can be done as follows:

```js
const navigate = useNavigate();
navigate("/welcome", { replace: true });
```

- v5's "Prompt" component is deprecated in v6. Currently there is no replacement.
