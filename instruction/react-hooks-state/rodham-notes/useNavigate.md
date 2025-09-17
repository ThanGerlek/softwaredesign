
# useNavigate

Call `useNavigate()` to access React's `navigate` function.

`navigate` lets you programmatically change your app's current route/URL.

## Example

```
import { useNavigate } from "react-router-dom";

function Home() {
  const navigate = useNavigate();

  return (
    <div>
      <h2>Home Page</h2>
      <button onClick={() => navigate("/about")}>Go to About</button>
    </div>
  );
}
```
