# Template Method Pattern

**Behavioral Pattern: Template Method**

---

## Definition
The Template Method pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses.

---

## When to Use
- When you want to define the outline of an algorithm but allow subclasses to implement specific steps.

---

## Real MERN Use Case
Use the Template Method pattern to define request processing pipelines, where certain steps can be customized in subclasses.

---

## JavaScript Example
```js
class DataProcessor {
  process() {
    this.fetch();
    this.transform();
    this.save();
  }
  fetch() {}
  transform() {}
  save() {}
}

class UserProcessor extends DataProcessor {
  fetch() { console.log('Fetching users'); }
  transform() { console.log('Transforming users'); }
  save() { console.log('Saving users'); }
}
```

---

## TypeScript Example
```ts
abstract class DataProcessor {
  process() {
    this.fetch();
    this.transform();
    this.save();
  }
  abstract fetch(): void;
  abstract transform(): void;
  abstract save(): void;
}

class UserProcessor extends DataProcessor {
  fetch() { console.log('Fetching users'); }
  transform() { console.log('Transforming users'); }
  save() { console.log('Saving users'); }
}
```

---

## Pros
- Promotes code reuse
- Defines algorithm structure clearly

## Cons
- Can lead to rigid class hierarchies
- May be harder to understand for simple cases