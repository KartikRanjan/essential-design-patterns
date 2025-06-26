# Builder Pattern

**Creational Pattern: Builder**

---

## Definition
The Builder pattern separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

---

## When to Use
- When you need to construct complex objects step by step.
- When the construction process should allow different representations.

---

## Real MERN Use Case
Use the Builder pattern to create complex query objects for MongoDB or to build configuration objects for Express middleware.

---

## JavaScript Example
```js
class UserBuilder {
  constructor(name) { this.name = name; }
  setAge(age) { this.age = age; return this; }
  setEmail(email) { this.email = email; return this; }
  build() { return this; }
}

const user = new UserBuilder('Alice').setAge(30).setEmail('alice@email.com').build();
```

---

## TypeScript Example
```ts
class User {
  constructor(public name: string, public age?: number, public email?: string) {}
}

class UserBuilder {
  private name: string;
  private age?: number;
  private email?: string;

  constructor(name: string) { this.name = name; }
  setAge(age: number) { this.age = age; return this; }
  setEmail(email: string) { this.email = email; return this; }
  build() { return new User(this.name, this.age, this.email); }
}

const user = new UserBuilder('Alice').setAge(30).setEmail('alice@email.com').build();
```

---

## Pros
- Step-by-step object construction
- Improves code readability

## Cons
- Can add extra classes
- May be overkill for simple objects