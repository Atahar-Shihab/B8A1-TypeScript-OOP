# What is Type Narrowing in TypeScript?

## Introduction
In TypeScript, we often work with union types like `string | number`. When a variable can have multiple types, TypeScript cannot be sure which type is active. Without narrowing, TypeScript throws an error when calling type-specific methods. Type narrowing means checking the type at runtime so TypeScript knows the exact type. This helps us write clean, safe code.

## Common Narrowing Methods

### 1. The `typeof` Check
The `typeof` operator is the simplest way to check primitive types like strings, numbers, and booleans. Inside the `if` check, TypeScript narrows the variable safely.

```ts
function printId(id: string | number): void {
  if (typeof id === "string") {
    console.log(id.toUpperCase());
  } else {
    console.log(id * 2);
  }
}
```

### 2. The `instanceof` Check
We use `instanceof` to check if an object is created from a class or a constructor like `Date`. It allows safe access to instance methods and properties.

```ts
function formatDate(value: Date | string): string {
  if (value instanceof Date) {
    return value.toISOString();
  }
  return value;
}
```

### 3. The `in` Operator
The `in` operator checks if an object has a particular property. This is very useful to distinguish different object shapes in a union. You do not need classes for this.

```ts
type Fish = { swim: () => void };
type Bird = { fly: () => void };

function moveAnimal(animal: Fish | Bird): void {
  if ("swim" in animal) {
    animal.swim();
  } else {
    animal.fly();
  }
}
```

## Conclusion
Type narrowing is a core concept in TypeScript. By using simple checks like `typeof`, `instanceof`, and `in`, we can handle union types safely. It prevents runtime errors and makes our code much more reliable.
