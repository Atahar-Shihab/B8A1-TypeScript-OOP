# Differences Between Type Aliases and Interfaces in TypeScript

## Introduction
When structuring data in TypeScript, defining clear contracts for objects is essential. TypeScript offers two primary tools for this purpose: type aliases and interfaces. While both can describe object shapes and often seem interchangeable, they possess fundamental differences in how they behave and when they should be used.

## Core Differences

### 1. Declaration Merging
Interfaces support declaration merging. When you define multiple interfaces with the identical name in the same scope, TypeScript automatically combines their properties into a single interface. Type aliases do not allow this; attempting to declare the same type name twice results in a compilation error.

```ts
interface User {
  id: number;
}
interface User {
  name: string;
}
```

### 2. Extending vs Intersection
Interfaces extend other interfaces using the familiar `extends` keyword, creating clean inheritance hierarchies. In contrast, type aliases achieve composition by combining types using intersection operators (`&`).

```ts
interface Admin extends User {
  role: string;
}

type Employee = { id: number } & { department: string };
```

### 3. Flexibility with Types
Type aliases are significantly more versatile. A type alias can define primitive types, union types, intersection types, and tuples. An interface is restricted to defining the shape of an object or a function.

```ts
type Status = "active" | "inactive";
type Coordinate = [number, number];
```

## When to Choose Which
Use an `interface` when building libraries, object-oriented systems, or public APIs where consumers might need declaration merging. Use a `type` alias when working with unions, tuples, primitive aliases, or complex functional types.

## Conclusion
Both type aliases and interfaces are foundational features in TypeScript. For basic object shapes, both work reliably. Choosing between them comes down to whether you need interface extensibility and merging or the broader composition power of types.
