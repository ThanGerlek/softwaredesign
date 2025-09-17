# Non-DOM uses of useRef

### Like `useState`, `useRef` can be used to persist values across re-renders.
### Unlike `useState`, modifying `useRef` values does not cause a re-render.

## Storing mutable values that survive re-renders

```
function Counter() {
  const countRef = React.useRef(0);

  function handleClick() {
    countRef.current++;
    console.log("Clicked", countRef.current, "times");
  }

  return <button onClick={handleClick}>Click me</button>;
}
```

🔹 Here, the count persists across renders, but updating it won’t cause the component to re-render.

## Keeping track of previous values

```
function ValueTracker({ value }) {
  const prevValueRef = React.useRef();

  React.useEffect(() => {
    prevValueRef.current = value;
  }, [value]);

  return (
    <p>
      Current: {value}, Previous: {prevValueRef.current}
    </p>
  );
}
```

🔹 Useful for comparisons, diffing, or debugging.

## Storing IDs, timers, or external handles

```
function Timer() {
  const timerIdRef = React.useRef();

  function start() {
    timerIdRef.current = setInterval(() => {
      console.log("Tick...");
    }, 1000);
  }

  function stop() {
    clearInterval(timerIdRef.current);
  }

  return (
    <>
      <button onClick={start}>Start</button>
      <button onClick={stop}>Stop</button>
    </>
  );
}
```

🔹 You don’t want the timer ID in React state, because it doesn’t affect rendering — so a ref is perfect.

## Avoiding stale closures in effects/callbacks

```
function Chat({ message }) {
  const latestMessageRef = React.useRef(message);

  React.useEffect(() => {
    latestMessageRef.current = message;
  }, [message]);

  function handleSend() {
    // Always sends the latest message, even inside async callbacks
    sendToServer(latestMessageRef.current);
  }

  return <button onClick={handleSend}>Send</button>;
}
```

🔹 Here, refs prevent bugs where effects capture old values.

## Flagging values across renders without re-rendering

```
function FirstRenderOnly() {
  const isFirstRender = React.useRef(true);

  React.useEffect(() => {
    if (isFirstRender.current) {
      console.log("Only on first render");
      isFirstRender.current = false;
    }
  });
  return <div>Check console</div>;
}
```

🔹 A common trick for first-render detection.
