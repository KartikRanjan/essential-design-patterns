# Proxy Pattern

**Structural Pattern: Proxy**

---

## Definition
The Proxy pattern provides a surrogate or placeholder for another object to control access to it.

---

## When to Use
- When you need to control access to an object.
- When you want to add additional functionality (e.g., logging, caching) to an object.

---

## Real MERN Use Case
Use the Proxy pattern to add caching or access control to database queries in a MERN app.

---

## JavaScript Example
```js
const user = { name: 'Alice' };
const proxy = new Proxy(user, {
  get(target, prop) {
    console.log(`Accessed ${prop}`);
    return target[prop];
  }
});
console.log(proxy.name);
```

---

## TypeScript Example
```ts
interface IUser {
  name: string;
}

const user: IUser = { name: 'Alice' };
const proxy = new Proxy(user, {
  get(target, prop: keyof IUser) {
    console.log(`Accessed ${String(prop)}`);
    return target[prop];
  }
});
console.log(proxy.name);
```

---

## Pros
- Controls access to objects
- Adds extra functionality transparently

## Cons
- Can add complexity
- May impact performance