# Observer Pattern

**Behavioral Pattern: Observer**

---

## Definition
The Observer pattern defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

---

## When to Use
- When an object should notify other objects without knowing who they are.
- When you want to implement event handling systems.

---

## Real MERN Use Case
Use the Observer pattern to implement real-time notifications or event-driven updates in a MERN app (e.g., using websockets).

---

## JavaScript Example
```js
class Subject {
  constructor() { this.observers = []; }
  subscribe(fn) { this.observers.push(fn); }
  notify(data) { this.observers.forEach(fn => fn(data)); }
}

const subject = new Subject();
subject.subscribe(data => console.log('Received:', data));
subject.notify('Hello!');
```

---

## TypeScript Example
```ts
class Subject<T> {
  private observers: ((data: T) => void)[] = [];
  subscribe(fn: (data: T) => void) { this.observers.push(fn); }
  notify(data: T) { this.observers.forEach(fn => fn(data)); }
}

const subject = new Subject<string>();
subject.subscribe(data => console.log('Received:', data));
subject.notify('Hello!');
```

---

## Pros
- Promotes loose coupling
- Supports event-driven programming

## Cons
- Can be hard to debug
- May lead to memory leaks if not managed