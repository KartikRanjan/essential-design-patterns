# Decorator Pattern

**Structural Pattern: Decorator**

---

## Definition
The Decorator pattern allows behavior to be added to individual objects, dynamically, without affecting the behavior of other objects from the same class.

---

## When to Use
- When you want to add responsibilities to objects dynamically and transparently.
- When subclassing is impractical.

---

## Real MERN Use Case
Use the Decorator pattern to add logging, authentication, or caching to Express route handlers without modifying their code.

---

## JavaScript Example
```js
function logger(fn) {
  return function(...args) {
    console.log('Arguments:', args);
    return fn(...args);
  };
}

function add(a, b) { return a + b; }
const loggedAdd = logger(add);
```

---

## TypeScript Example
```ts
function logger<T extends (...args: any[]) => any>(fn: T): T {
  return ((...args: any[]) => {
    console.log('Arguments:', args);
    return fn(...args);
  }) as T;
}

function add(a: number, b: number) { return a + b; }
const loggedAdd = logger(add);
```

---

## Pros
- Adds behavior without modifying code
- Promotes code reuse

## Cons
- Can lead to many small classes/functions
- May make debugging harder