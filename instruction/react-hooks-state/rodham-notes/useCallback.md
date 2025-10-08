
# useCallback

`useCallback` is used to re-create functions only when necessary.

## Example 1

Components often pass callback functions to sub-components.

Re-creating such a callback function will force a re-render of the child component.

We want to re-create callback functions only when their functionality actually changes.

```
import React, { useState, useCallback } from "react";

// Child component
const Child = React.memo(({ onClick }) => {
  console.log("Child rendered");
  return <button onClick={onClick}>Click me</button>;
});

function Parent() {
  const [count, setCount] = useState(0);

  // Without useCallback, a new function gets created every render,
  // so <Child> will always re-render unnecessarily.
  
  // const handleClick = () => console.log("Button clicked");
  const handleClick = useCallback(() => console.log("Button clicked"), []); // ✅ stable reference across renders

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(c => c + 1)}>Increment Count</button>
      <Child onClick={handleClick} />
    </div>
  );
}
```

## Example 2

Sometimes functions are used as dependencies for `useEffect`, `useMemo`, and `useCallback`.

We want to re-create dependency functions only when their functionality actually changes.

```
function Component() {

  // Without useCallback, a new function gets created every render,
  // so useEffect will always execute unnecessarily.

  // const fn = () => {
  //   console.log("hello");
  //   console.log("world");
  // };

  const fn = useCallback(() => {
    console.log("hello");
    console.log("world");
  }, []);

  useEffect(() => {
    console.log("fresh render");
    fn();
  }, [fn]);

  ...
}
```

## `useMemo` and `useCallback`

`useMemo` and `useCallback` are very similar.

`useMemo` is used to cache values, and recompute them when dependencies change.

`useCallback` is used to cache functions, and recreate them when dependencies change.
