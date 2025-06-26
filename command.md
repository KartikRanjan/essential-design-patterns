# Command Pattern

**Behavioral Pattern: Command**

---

## Definition
The Command pattern encapsulates a request as an object, allowing you to parameterize clients with different requests, queue or log requests, and support undoable operations.

---

## When to Use
- When you need to parameterize objects with operations.
- When you want to support undo/redo or logging of operations.

---

## Real MERN Use Case
Use the Command pattern to implement actions in a Redux-like state management system or to queue database operations.

---

## JavaScript Example
```js
class Command {
  execute() {}
}

class AddUserCommand extends Command {
  constructor(user) { super(); this.user = user; }
  execute() { return `User ${this.user} added`; }
}

function run(command) { return command.execute(); }
```

---

## TypeScript Example
```ts
interface ICommand {
  execute(): string;
}

class AddUserCommand implements ICommand {
  constructor(private user: string) {}
  execute() { return `User ${this.user} added`; }
}

function run(command: ICommand) { return command.execute(); }
```

---

## Pros
- Decouples sender and receiver
- Supports undo/redo

## Cons
- Can add extra classes
- May increase complexity