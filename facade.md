# Facade Pattern

**Structural Pattern: Facade**

---

## Definition
The Facade pattern provides a simplified interface to a complex subsystem, making it easier to use.

---

## When to Use
- When you want to provide a simple interface to a complex system.
- When you want to decouple a subsystem from its clients.

---

## Real MERN Use Case
Use the Facade pattern to wrap multiple database operations or third-party APIs behind a single, easy-to-use interface.

---

## JavaScript Example
```js
class Database {
  connect() { return 'Connected'; }
  disconnect() { return 'Disconnected'; }
}

class DatabaseFacade {
  constructor() { this.db = new Database(); }
  start() { return this.db.connect(); }
  stop() { return this.db.disconnect(); }
}
```

---

## TypeScript Example
```ts
class Database {
  connect(): string { return 'Connected'; }
  disconnect(): string { return 'Disconnected'; }
}

class DatabaseFacade {
  private db = new Database();
  start() { return this.db.connect(); }
  stop() { return this.db.disconnect(); }
}
```

---

## Pros
- Simplifies complex systems
- Reduces dependencies

## Cons
- May become a god object
- Can hide important details