**Creational Pattern: Factory**

---

## Definition
The Factory pattern provides an interface for creating objects but allows subclasses or methods to alter the type of objects that will be created.

---

## When to Use
- When you need to create many objects that share the same interface but may require different implementations.

---

## Real MERN Use Case
Use the Factory pattern to create different types of database connectors (e.g., MongoDB, Redis) depending on the environment.

---

## JavaScript Example
```js
class User {
  constructor(name) {
    this.name = name;
  }
}

class Admin {
  constructor(name) {
    this.name = name;
    this.admin = true;
  }
}

function userFactory(type, name) {
  if (type === 'admin') return new Admin(name);
  return new User(name);
}
```

---

## TypeScript Example
```ts
interface IUser {
  name: string;
}

class User implements IUser {
  constructor(public name: string) {}
}

class Admin implements IUser {
  constructor(public name: string, public admin: boolean = true) {}
}

function userFactory(type: 'user' | 'admin', name: string): IUser {
  return type === 'admin' ? new Admin(name) : new User(name);
}
```

---

## Pros
- Encapsulates object creation
- Promotes reusability
- Centralized control

## Cons
- Adds extra layer of abstraction
- May increase complexity if overused