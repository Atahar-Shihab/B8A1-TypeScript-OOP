# Understanding Type Narrowing in TypeScript

## Introduction
In TypeScript, variables often start with broad types, especially when using union types like `string | number`. Working directly with union types can sometimes be restrictive because TypeScript does not know the exact value at runtime. Type narrowing is the mechanism where TypeScript refines a broad type into a more specific type within conditional blocks. This process allows developers to access type-specific methods safely. It also prevents common runtime bugs in modern applications.

## Core Narrowing Techniques

### 1. The `typeof` Operator
The `typeof` type guard is the simplest way to inspect primitive values. It works with strings, numbers, booleans, and symbols. Inside the check, TypeScript safely narrows the variable.

```ts
function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.trim().toLowerCase();
  }
  return value.toFixed(2);
}
```

### 2. The `instanceof` Operator
The `instanceof` operator checks if an object belongs to a particular class. It is very useful when working with custom classes, errors, or standard objects like `Date`. By checking the prototype chain, TypeScript ensures safe property access.

```ts
function printDate(input: Date | string): string {
  if (input instanceof Date) {
    return input.toISOString();
  }
  return input;
}
```

### 3. The `in` Operator
The `in` operator checks if a specific property exists on an object. This is extremely helpful when working with distinct object shapes in a union. It lets you differentiate objects without needing full class definitions.

```ts
type Dog = { bark: () => void };
type Cat = { meow: () => void };

function handlePet(pet: Dog | Cat): void {
  if ("bark" in pet) {
    pet.bark();
  } else {
    pet.meow();
  }
}
```

## Conclusion
Type narrowing is a core strength of TypeScript. By combining runtime checks like `typeof`, `instanceof`, and `in` with static type checking, TypeScript provides confidence and safety. Writing reliable code becomes much easier when you let type narrowing guide your logic.
