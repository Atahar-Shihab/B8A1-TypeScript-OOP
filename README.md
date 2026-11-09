# B8A1: Problem Solving with TypeScript & OOP

This repository contains the solutions and technical blog posts for **Assignment 1 (Batch 8)** of Programming Hero Level-2 Web Development course. The assignment covers foundational and intermediate TypeScript concepts from Modules 1, 2, and 3, focusing on clean typing, type narrowing, generics, asynchronous operations, and Object-Oriented Programming (OOP).

---

## 📁 Repository Structure

```text
├── solutions.ts
├── type-vs-interface.md
├── union-and-intersection.md
└── README.md
```

---

## 📝 Overview of Problem Solutions (`solutions.ts`)

All required functions and classes are implemented in `solutions.ts` using strict TypeScript typing with zero `any` types:

1. **`multiplyValue(value, multiplier)`**: Multiplies `value` by `multiplier`. If `multiplier` is omitted (`undefined`), it defaults to multiplying by 2. Correctly handles `0` without falsy coercion issues.
2. **`processInput(input)`**: Accepts `string | number | boolean`. Uses `typeof` type narrowing to lowercase trimmed strings, multiply numbers by 10, or format booleans as `"Active"` or `"Inactive"`.
3. **`formatCoordinate(coordinate)`**: Accepts a `readonly [number, number, string]` tuple and formats it into `"Location: [locationName] ([latitude], [longitude])"` while preventing tuple mutation.
4. **`concatenateArrays(...arrays)`**: A generic function using rest parameters (`...arrays: T[][]`) that combines multiple arrays of type `T` into a single array in sequence.
5. **`Course` & `getPopularCourses(courses, minStudents)`**: Defines the `Course` interface and filters published courses having students greater than or equal to `minStudents` without mutating the input array.
6. **`pluckValues(items, key)`**: A generic utility function using `<T, K extends keyof T>` to pluck property values across an array of objects while preserving type safety.
7. **`Employee` & `Manager`**: Demonstrates Object-Oriented Programming (OOP) principles using `protected` and `private` access modifiers, inheritance via `extends`, constructor chaining with `super()`, and method implementation.
8. **`validateAgeAsync(age)`**: An asynchronous function returning `Promise<string>`. Resolves with `"Access Granted"` after 1 second (1000ms) if age is 18 or above; immediately rejects with an `Error("Access Denied: Must be 18 or older")` if under 18.

---

## 📚 Technical Blog Posts

Read the two technical blog posts included in this repository:

1. [**Differences Between Type Aliases and Interfaces in TypeScript**](./type-vs-interface.md)  
   *An in-depth guide explaining declaration merging, type extension vs. intersection, primitive/union flexibility, and when to use each.*

2. [**Combining Union and Intersection Types in TypeScript**](./union-and-intersection.md)  
   *A beginner-friendly practical guide demonstrating how to combine union (`|`) and intersection (`&`) types to model real-world user roles safely.*

---

## 🚀 How to Run and Test

Ensure you have [Node.js](https://nodejs.org/) installed on your machine.

1. **Verify TypeScript compilation:**
   ```bash
   npx tsc --noEmit --strict solutions.ts
   ```

2. **Execute with tsx or ts-node:**
   ```bash
   npx tsx solutions.ts
   ```
