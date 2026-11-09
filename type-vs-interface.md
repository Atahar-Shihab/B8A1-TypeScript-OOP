# Difference Between Type Alias and Interface in TypeScript

## Introduction
When learning TypeScript, we often need to define the structure of our data and objects. TypeScript gives us two main ways to do this: `type` and `interface`. At first glance, they look almost the same. However, they have some important differences that every beginner should know.

## Key Differences

### 1. Declaration Merging
One big difference is declaration merging. If you write two interfaces with the same name, TypeScript joins them together into one single interface. But if you try to do the same thing with a `type`, TypeScript will give an error.

```ts
interface User {
  id: number;
}

interface User {
  name: string;
}
```

### 2. Extending and Combining
We can extend an `interface` by using the `extends` keyword. This feels very natural if you know object-oriented programming. For `type`, we do not use `extends`. Instead, we combine them using the `&` (intersection) operator.

```ts
interface Admin extends User {
  role: string;
}

type Person = { id: number } & { name: string };
```

### 3. Working with Basic Types and Unions
A `type` is more flexible than an `interface`. You can use `type` to create union types, primitive aliases, and tuples. An `interface` cannot do this because it is only made for object shapes.

```ts
type Status = "pending" | "success" | "error";
type Coordinates = [number, number];
```

## When Should You Use Which?
Use `interface` when you are creating standard object shapes or working with classes and OOP. Use `type` when you need unions, tuples, or simple type aliases.

## Conclusion
Both `type` and `interface` are very useful in TypeScript. For normal objects, you can use either one. But knowing these simple differences helps you write cleaner and better TypeScript code in your projects.
