# Prototype Pattern

**Creational Pattern: Prototype**

---

## Definition
The Prototype pattern creates new objects by copying an existing object, known as the prototype.

---

## When to Use
- When the cost of creating a new object is expensive.
- When you want to avoid subclassing.

---

## Real MERN Use Case
Use the Prototype pattern to clone configuration objects or database schemas in a MERN app.

---

## JavaScript Example
```js
const userPrototype = {
  greet() { return `Hello, ${this.name}`; }
};

const user = Object.create(userPrototype);
user.name = 'Alice';
console.log(user.greet());
```

---

## TypeScript Example
```ts
interface IUser {
  name: string;
  greet(): string;
}

const userPrototype: IUser = {
  name: '',
  greet() { return `Hello, ${this.name}`; }
};

const user = Object.create(userPrototype);
user.name = 'Alice';
console.log(user.greet());
```

---

## Pros
- Reduces the need for subclassing
- Can improve performance

## Cons
- Cloning complex objects can be tricky
- May lead to unexpected side effects