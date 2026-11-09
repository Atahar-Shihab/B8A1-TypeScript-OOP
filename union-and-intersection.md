# Combining Union and Intersection Types in TypeScript

## Introduction
In TypeScript, union types (`|`) and intersection types (`&`) are two core features. A union type means a value can be one type or another. An intersection type combines multiple types into one single type. Both features are very useful on their own. When we combine them together, we can model real-world data in a clean and safe way.

## Practical Example: User Roles with Common Data

Imagine we are building an app with different user types, like an Admin and a Customer. Every user shares common information like `id` and `name`. However, an Admin has specific permissions, while a Customer has reward points. This is a very common requirement in web applications.

Instead of repeating the common fields in every type, we can combine them. We use an intersection to attach the base data to a union of specific roles:

```ts
type BaseUser = {
  id: number;
  name: string;
};

type Admin = {
  role: "admin";
  permissions: string[];
};

type Customer = {
  role: "customer";
  loyaltyPoints: number;
};

type AppUser = BaseUser & (Admin | Customer);
```

## How It Works in Practice
With `AppUser`, every user must have an `id` and `name`. Then, based on the `role`, TypeScript knows which extra fields are required. This ensures complete type safety across our application:

```ts
const adminUser: AppUser = {
  id: 1,
  name: "Rakib",
  role: "admin",
  permissions: ["create", "delete"]
};

const customerUser: AppUser = {
  id: 2,
  name: "Sadia",
  role: "customer",
  loyaltyPoints: 150
};
```

If we try to create an admin without `permissions`, TypeScript will show an error immediately. It also stops us from adding customer fields to an admin.

## Conclusion
Combining union and intersection types helps us write reusable code without repeating fields. It gives us the flexibility of multiple options while keeping shared properties required. This pattern is very popular in TypeScript and makes code much easier to maintain.
