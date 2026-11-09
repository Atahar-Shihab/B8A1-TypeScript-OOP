# Assignment 1 - TypeScript & OOP (B8A1)

This repository contains my solutions for Assignment 1 of Programming Hero Level 2 (Batch 8). In this assignment, I solved 8 TypeScript problems and wrote 2 technical blog posts.

## Project Overview

All problems are solved in the `solutions.ts` file without using `any` type:

1. **multiplyValue**: Multiplies a number by an optional multiplier (defaults to 2). Handles 0 properly.
2. **processInput**: Takes a string, number, or boolean and formats it using `typeof` type narrowing.
3. **formatCoordinate**: Uses a readonly tuple to return a formatted location string.
4. **concatenateArrays**: A generic function with rest parameters that merges multiple arrays of the same type.
5. **getPopularCourses**: Filters courses from a `Course` interface where published is true and student count meets the minimum.
6. **pluckValues**: A generic function using `keyof` to extract values of a specific key from an array of objects.
7. **Employee and Manager**: OOP classes using `protected` and `private` access modifiers with inheritance.
8. **validateAgeAsync**: An async function returning a Promise that resolves if age is 18 or above, or rejects with an Error if below 18.

## Blog Posts

Here are the links to my two technical blog posts:

- [Blog 1: Difference Between Type Alias and Interface in TypeScript](./type-vs-interface.md)
- [Blog 2: Combining Union and Intersection Types in TypeScript](./union-and-intersection.md)

## How to Run

To run and test the file:

```bash
npx tsx solutions.ts
```
