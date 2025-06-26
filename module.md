# Module Pattern

**Structural Pattern: Module**

---

## Definition
The Module pattern encapsulates related code into a single unit, exposing only what is necessary and hiding the rest.

---

## When to Use
- When you want to organize code into reusable, self-contained units.
- When you want to control the visibility of variables and functions.

---

## Real MERN Use Case
Use the Module pattern to organize utility functions, database logic, or configuration in a MERN app.

---

## JavaScript Example
```js
const UserModule = (function() {
  let users = [];
  function addUser(user) { users.push(user); }
  function getUsers() { return users; }
  return { addUser, getUsers };
})();
```

---

## TypeScript Example
```ts
module UserModule {
  let users: string[] = [];
  export function addUser(user: string) { users.push(user); }
  export function getUsers() { return users; }
}
```

---

## Pros
- Encapsulates code
- Prevents global namespace pollution

## Cons
- Can be less flexible than classes
- May be harder to test