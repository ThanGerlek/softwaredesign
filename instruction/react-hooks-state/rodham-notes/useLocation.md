
# useLocation

Call `useLocation()` to get information about the current route (URL).

`useLocation` returns an object like this:

```
{
  pathname: "/about",
  search: "?q=react",
  hash: "#section2",
  state: someCustomState,
  key: "abc123"
}
```

## Example

```
import { useLocation } from "react-router-dom";

function ShowLocation() {
  const location = useLocation();
  return (
    <div>
      <h3>Current Path: {location.pathname}</h3>
      <p>Search Query: {location.search}</p>
      <p>Hash: {location.hash}</p>
    </div>
  );
}
