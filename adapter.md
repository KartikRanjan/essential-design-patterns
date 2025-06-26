# Adapter Pattern

**Structural Pattern: Adapter**

---

## Definition
The Adapter pattern allows objects with incompatible interfaces to work together by wrapping an existing class with a new interface.

---

## When to Use
- When you want to use an existing class, but its interface does not match the one you need.

---

## Real MERN Use Case
Use the Adapter pattern to integrate third-party libraries (e.g., a legacy authentication system) into your MERN app with a unified interface.

---

## JavaScript Example
```js
class OldApi {
  getData() { return 'old data'; }
}

class NewApi {
  fetch() { return 'new data'; }
}

class ApiAdapter {
  constructor() { this.api = new NewApi(); }
  getData() { return this.api.fetch(); }
}
```

---

## TypeScript Example
```ts
interface IDataApi {
  getData(): string;
}

class OldApi implements IDataApi {
  getData() { return 'old data'; }
}

class NewApi {
  fetch() { return 'new data'; }
}

class ApiAdapter implements IDataApi {
  private api = new NewApi();
  getData() { return this.api.fetch(); }
}
```

---

## Pros
- Increases code reusability
- Allows integration of legacy code

## Cons
- Can add extra complexity
- May lead to too many adapters if overused