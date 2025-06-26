# Chain Of Responsibility Pattern

**Behavioral Pattern: Chain of Responsibility**

---

## Definition
The Chain of Responsibility pattern passes a request along a chain of handlers, allowing each handler to process the request or pass it to the next handler in the chain.

---

## When to Use
- When more than one object may handle a request and the handler isn't known in advance.
- When you want to decouple senders and receivers.

---

## Real MERN Use Case
Use the Chain of Responsibility pattern to implement Express middleware, where each middleware can handle or pass the request.

---

## JavaScript Example
```js
class Handler {
  setNext(handler) { this.next = handler; return handler; }
  handle(request) { if (this.next) return this.next.handle(request); }
}

class AuthHandler extends Handler {
  handle(request) {
    if (!request.user) return 'Unauthorized';
    return super.handle(request);
  }
}

class DataHandler extends Handler {
  handle(request) {
    if (request.data) return 'Data processed';
    return super.handle(request);
  }
}
```

---

## TypeScript Example
```ts
interface IRequest { user?: string; data?: any; }

abstract class Handler {
  protected next?: Handler;
  setNext(handler: Handler) { this.next = handler; return handler; }
  handle(request: IRequest): string | undefined {
    if (this.next) return this.next.handle(request);
  }
}

class AuthHandler extends Handler {
  handle(request: IRequest) {
    if (!request.user) return 'Unauthorized';
    return super.handle(request);
  }
}

class DataHandler extends Handler {
  handle(request: IRequest) {
    if (request.data) return 'Data processed';
    return super.handle(request);
  }
}
```

---

## Pros
- Decouples sender and receiver
- Flexible chain structure

## Cons
- Can be hard to debug
- May lead to unhandled requests