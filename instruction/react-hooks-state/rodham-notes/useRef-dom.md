# Using useRef for direct DOM element access

## Focusing an input automatically

```
import React, { useRef, useEffect } from "react";

function AutoFocusInput() {
  const inputRef = useRef(null);

  useEffect(() => {
    inputRef.current.focus(); // directly call DOM method
  }, []);

  return <input ref={inputRef} placeholder="Type here..." />;
}
```

🔹 This is the classic “focus an input on mount” case. React itself doesn’t provide a declarative way to do this.

## Positioning a tooltip

```
import React, { useRef, useState, useEffect } from "react";

function TooltipButton() {
  const btnRef = useRef(null);
  const [tooltipPos, setTooltipPos] = useState({ top: 0, left: 0 });

  useEffect(() => {
    if (btnRef.current) {
      const rect = btnRef.current.getBoundingClientRect();
      setTooltipPos({ top: rect.bottom + 5, left: rect.left });
    }
  }, []);

  return (
    <>
      <button ref={btnRef}>Hover me</button>
      <div
        style={{
          position: "absolute",
          top: tooltipPos.top,
          left: tooltipPos.left,
          background: "black",
          color: "white",
          padding: "4px 8px",
        }}
      >
        Tooltip!
      </div>
    </>
  );
}
```

🔹 The tooltip needs pixel coordinates from the real DOM element.

## Controlling a video player

```
import React, { useRef } from "react";

function VideoPlayer() {
  const videoRef = useRef(null);

  return (
    <div>
      <video ref={videoRef} width="320" controls>
        <source src="video.mp4" type="video/mp4" />
      </video>
      <br />
      <button onClick={() => videoRef.current.play()}>Play</button>
      <button onClick={() => videoRef.current.pause()}>Pause</button>
    </div>
  );
}
```

🔹 React doesn’t have play() or pause() props — you must call the DOM API.

## Integrating with a third-party library (Chart.js)

```
import React, { useRef, useEffect } from "react";
import Chart from "chart.js/auto";

function ChartExample() {
  const canvasRef = useRef(null);

  useEffect(() => {
    const ctx = canvasRef.current.getContext("2d");
    new Chart(ctx, {
      type: "bar",
      data: { labels: ["A", "B", "C"], datasets: [{ data: [12, 19, 3] }] },
    });
  }, []);

  return <canvas ref={canvasRef} />;
}
```

🔹 Chart.js needs a real `<canvas>` element to draw into.
