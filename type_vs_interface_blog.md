# Type Aliases vs Interfaces in TypeScript

## Introduction
There are two primary ways in typescript of writing data structure - type aliases and interfaces. Although they work like same things for basic things but they type and interface work in different ways internally. They can be used based on the right situation for writing a well structured code.

## Details
Interface are are mainly designed for being the blueprint for object and classes. They can hold combination of declarations. Same Interface can be declared twice and typescript will merge them into one making them one interface. This is handy in many situations.

```typescript
interface User {
  name: string;
}

interface User {
  age: number;
}

const myUser: User = { name: "Alice", age: 25 };
```

On the other hand, type alias are flexible and versatile. Interfaces are restricted to object like structure but type aliases can be used for primitive, arrays, tuple and complex structure of union. For storing variable like either string or a number, type alias is the way as interface is restricted to object only. So union structure can't be used with interface.

```typescript
type ID = string | number;

const studentId: ID = 21;
const employeeId: ID = "EM-1";
```

## Conclusion
There is a good rule of thumb. When defining the shape of object, the rule is to use interface always. Interface's best use cases are in classes and object oriented programming. Type alias can be used to create any union, intersections, tuples and custom primitive types.