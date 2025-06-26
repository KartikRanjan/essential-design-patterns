# Singleton Pattern

**Creational Pattern: Singleton**

---

## Definition
The Singleton pattern ensures a class has only one instance and provides a global point of access to it.

---

## When to Use
- When you need exactly one instance of a class.
- When you want to control access to shared resources.

---

## Real MERN Use Case
Use the Singleton pattern for database connections or configuration objects in a MERN app.

---

## JavaScript Example
```js
class Singleton {
  constructor() {
    if (Singleton.instance) return Singleton.instance;
    Singleton.instance = this;
  }
}

const a = new Singleton();
const b = new Singleton();
console.log(a === b); // true
```

---

## TypeScript Example
```ts
class Singleton {
  private static instance: Singleton;
  private constructor() {}
  static getInstance() {
    if (!Singleton.instance) Singleton.instance = new Singleton();
    return Singleton.instance;
  }
}

const a = Singleton.getInstance();
const b = Singleton.getInstance();
console.log(a === b); // true
```

---

## Pros
- Ensures a single instance
- Controls access to resources

## Cons
- Can make testing difficult
- May introduce global state