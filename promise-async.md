# Promise Async Pattern

**Asynchronous Pattern: Promise/Async**

---

## Definition
The Promise/Async pattern handles asynchronous operations, allowing you to write non-blocking code using promises or async/await syntax.

---

## When to Use
- When you need to handle asynchronous operations like API calls, file I/O, or timers.
- When you want to avoid callback hell.

---

## Real MERN Use Case
Use the Promise/Async pattern to handle database queries, HTTP requests, or any asynchronous logic in a MERN app.

---

## JavaScript Example
```js
function fetchData() {
  return new Promise(resolve => setTimeout(() => resolve('data'), 1000));
}

fetchData().then(data => console.log(data));
```

---

## TypeScript Example
```ts
async function fetchData(): Promise<string> {
  return new Promise(resolve => setTimeout(() => resolve('data'), 1000));
}

(async () => {
  const data = await fetchData();
  console.log(data);
})();
```

---

## Pros
- Simplifies async code
- Avoids callback hell

## Cons
- Can be hard to debug
- Error handling can be tricky