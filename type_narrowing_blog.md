# Type Narrowing in TypeScript

## Introduction

The variables can be declared often with multiple types (string, number, boolean) when using type alias or function parameter in typescript. This variables' types can be refined to a specific type by using logical validation like truthiness, if else, type guard etc. These refinement of types is called type narrowing.

## Details

Typeof operator is the most common way of inspecting the primitive values. If a parameter in function recieves either a string or number, the type can be checked in 'if' statement with typeof if the type is string or number.

```typescript
function checkString(input: number | string) {
  if (typeof input === "string") {
    console.log(input.toUpperCase());
  } else {
    console.log(input * 10);
  }
}
```

Another way is instanceof operator. It is used to check complex objects which are created using class. Like by using instance of, a custom error handler that recieves unknown types can be checked if its a instance of the built in javascript error class for safely accessing the message.

```typescript
function logError(error: unknown) {
  if (error instanceof Error) {
    console.log(error.message);
  }
}
```

There is another operator named 'in' to check if a exact property key exist or not in a javascript object. If a function recieves two kind of property, by using in type can be checked which object structure has passed in to determine the type of that object. This will check if the recieved input is exist on either of structure's key. If it finds a match, typescript can know which structure to passed on.

```typescript
type Fish = { swim: boolean };
type Bird = { fly: boolean };

function move(animal: Fish | Bird) {
  if ("swim" in animal) {
    console.log("It is a fish");
  }
}
```

## Conclusion

Type narrowing is a security gate for various types. Using type of, instaceof and in operator, predictable and crash free code can be written. By this way typescript compiler wont have any issues with many types.