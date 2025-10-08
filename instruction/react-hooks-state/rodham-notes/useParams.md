
# useParams

Call `useParams()` to access URL parameters defined in routes.

For example, if you define a route with a dynamic segment, e.g. `/users/:id`,
useParams() lets you access that `id` inside the component.

## Example

```
import { BrowserRouter, Routes, Route, useParams } from "react-router-dom";

function UserProfile() {
  const { id } = useParams(); // grab the "id" from the URL
  return <h2>User Profile for User ID: {id}</h2>;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/users/:id" element={<UserProfile />} />
      </Routes>
    </BrowserRouter>
  );
}
```
