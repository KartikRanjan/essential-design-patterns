# Strategy Pattern

**Behavioral Pattern: Strategy**

---

## Definition
The Strategy pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable.

---

## When to Use
- When you need to switch between different algorithms or behaviors at runtime.
- When you want to avoid large conditional statements.

---

## Real MERN Use Case
Use the Strategy pattern to select different authentication methods or payment gateways in a MERN app.

---

## JavaScript Example
```js
class AuthStrategy {
  authenticate() {}
}

class GoogleAuth extends AuthStrategy {
  authenticate() { return 'Google Auth'; }
}

class FacebookAuth extends AuthStrategy {
  authenticate() { return 'Facebook Auth'; }
}

class AuthContext {
  setStrategy(strategy) { this.strategy = strategy; }
  login() { return this.strategy.authenticate(); }
}
```

---

## TypeScript Example
```ts
interface AuthStrategy {
  authenticate(): string;
}

class GoogleAuth implements AuthStrategy {
  authenticate() { return 'Google Auth'; }
}

class FacebookAuth implements AuthStrategy {
  authenticate() { return 'Facebook Auth'; }
}

class AuthContext {
  private strategy: AuthStrategy;
  setStrategy(strategy: AuthStrategy) { this.strategy = strategy; }
  login() { return this.strategy.authenticate(); }
}
```

---

## Pros
- Promotes code flexibility
- Easy to add new strategies

## Cons
- Can add extra classes
- May be overkill for simple logic