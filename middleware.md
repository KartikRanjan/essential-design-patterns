# Middleware Pattern

---

## Definition
The Middleware pattern composes behavior in a pipeline, where each function can process input and pass control to the next function in the chain.

---

## When to Use
- When you want to process requests in stages.
- When you want to add cross-cutting concerns like logging, authentication, or error handling.

---

## Real MERN Use Case
Use the Middleware pattern in Express.js to handle HTTP requests, authentication, logging, and error handling.

---

## JavaScript Example
```js
function logger(req, res, next) {
  console.log('Request:', req.url);
  next();
}

function auth(req, res, next) {
  if (!req.user) return res.status(401).send('Unauthorized');
  next();
}

app.use(logger);
app.use(auth);
```

---

## TypeScript Example
```ts
import { Request, Response, NextFunction } from 'express';

function logger(req: Request, res: Response, next: NextFunction) {
  console.log('Request:', req.url);
  next();
}

function auth(req: Request, res: Response, next: NextFunction) {
  if (!req.user) return res.status(401).send('Unauthorized');
  next();
}
```

---

## Pros
- Modularizes request processing
- Easy to add/remove features

## Cons
- Order of middleware matters
- Can be hard to debug chains