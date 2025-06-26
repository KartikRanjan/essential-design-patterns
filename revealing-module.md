# Revealing Module Pattern

**Structural Pattern: Revealing Module**

---

## Definition
The Revealing Module pattern exposes only selected methods and properties, keeping the rest private within a closure.

---

## When to Use
- When you want to encapsulate private data and expose only a public API.

---

## Real MERN Use Case
Use the Revealing Module pattern to organize utility functions or sensitive logic in a MERN app, exposing only what is needed.

---

## JavaScript Example
```js
const Counter = (function() {
  let count = 0;
  function increment() { count++; }
  function getCount() { return count; }
  return { increment, getCount };
})();
```

---

## TypeScript Example
```ts
const Counter = (() => {
  let count = 0;
  function increment() { count++; }
  function getCount() { return count; }
  return { increment, getCount };
})();
```

---

## Pros
- Encapsulates private data
- Exposes a clear API

## Cons
- Can be less flexible than classes
- May be harder to test