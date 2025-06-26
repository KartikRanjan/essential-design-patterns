# State Pattern

**Behavioral Pattern: State**

---

## Definition
The State pattern allows an object to alter its behavior when its internal state changes, appearing to change its class.

---

## When to Use
- When an object's behavior depends on its state.
- When you want to avoid large conditional statements.

---

## Real MERN Use Case
Use the State pattern to manage user authentication states or UI modes in a MERN app.

---

## JavaScript Example
```js
class State {
  handle() {}
}

class LoggedInState extends State {
  handle() { return 'User is logged in'; }
}

class LoggedOutState extends State {
  handle() { return 'User is logged out'; }
}

class UserContext {
  setState(state) { this.state = state; }
  request() { return this.state.handle(); }
}
```

---

## TypeScript Example
```ts
interface State {
  handle(): string;
}

class LoggedInState implements State {
  handle() { return 'User is logged in'; }
}

class LoggedOutState implements State {
  handle() { return 'User is logged out'; }
}

class UserContext {
  private state: State;
  setState(state: State) { this.state = state; }
  request() { return this.state.handle(); }
}
```

---

## Pros
- Organizes code by state
- Avoids complex conditionals

## Cons
- Can add extra classes
- May be overkill for simple state changes