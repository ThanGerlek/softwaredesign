
# useMemo

`useMemo` is a hook used to memoize (cache) the result of an expensive calculation so that it only recomputes when its dependencies change.

If you have a function that does heavy computation or returns a value derived from props, state variables, or other variables, recalculating it on every render can hurt performance.

`useMemo` ensures that React reuses the cached value instead of recalculating unless one of the dependencies changes.

## Syntax

```
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

`computeExpensiveValue(a, b)` → function that does the work.

`[a, b]` → dependencies. The value is recomputed only if a or b changes.

## Simple Example

Without useMemo:

```
const result = expensiveCalculation(data);
```

This runs every render, even if data hasn’t changed.

With useMemo:

```
const result = useMemo(() => expensiveCalculation(data), [data]);
```

Now expensiveCalculation only runs when data changes.

## Realistic Example: Filtering and sorting a large list

Common useMemo use cases:

* Filtering
* Sorting
* Computing summary or statistical values for large data sets (e.g., totals, averages)

Imagine you have a big dataset (e.g., thousands of products), and you want to show only the items matching a search term, sorted alphabetically. Without useMemo, the filter and sort would run on every render, even if nothing relevant changed.

With useMemo, you only recompute when the input data or search term changes.

```
import { useState, useMemo } from "react";

const ProductList = ({ products }) => {
  const [search, setSearch] = useState("");

  // Expensive filter + sort operation
  const filteredProducts = useMemo(() => {
    console.log("Filtering and sorting..."); // runs only when dependencies change
    return products
      .filter((p) => p.name.toLowerCase().includes(search.toLowerCase()))
      .sort((a, b) => a.name.localeCompare(b.name));
  }, [products, search]); // ✅ dependencies

  return (
    <div>
      <input
        type="text"
        placeholder="Search products..."
        value={search}
        onChange={(e) => setSearch(e.target.value)}
      />

      <ul>
        {filteredProducts.map((p) => (
          <li key={p.id}>{p.name}</li>
        ))}
      </ul>
    </div>
  );
};
```

🔑 Why useMemo is useful here

Without useMemo: filtering + sorting runs on every keystroke and every render (even when search doesn’t change).

With useMemo: filtering + sorting runs only when products or search changes. If a parent re-renders but data/search didn’t change, React reuses the cached result.
