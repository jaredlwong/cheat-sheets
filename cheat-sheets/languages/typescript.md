## Escape Hatches
```typescript
let a: {b: string} | undefined
a!    // {b: string}: typescript will drop the undefined without checking
a?.b  // string | undefined: typescript will get b if a !== undefined
```



structural typing
void, never, null, 

index signatures

## Structural Typing
```typescript
class Zebra {
 trot() {
 // ...
 }
}
class Poodle {
 trot() {
 // ...
 }
}
function ambleAround(animal: Zebra) {
 animal.trot()
}
let zebra = new Zebra
let poodle = new Poodle
ambleAround(zebra) // OK
ambleAround(poodle) // OK
```

## Union and Intersection Types
Intersection types combine multiple types using the `&` operator. Unions types combine multiple types using the `|` operator. Intersection types can access all members. Union types can only access common members.

[Unions and Intersection Types](https://www.typescriptlang.org/docs/handbook/unions-and-intersections.html)

```typescript
type Cat = {name: string, purrs: boolean}
type Dog = {name: string, barks: boolean, wags: boolean}
type CatOrDogOrBoth = Cat | Dog
type CatAndDog = Cat & Dog

// Cat
let a: CatOrDogOrBoth = {name: 'Bonkers', purrs: true}
// Dog
a = {name: 'Domino', barks: true, wags: true}
// Both
a = {name: 'Donkers', barks: true, purrs: true, wags: true}
// You can only access common fields of union types
a.name  // Bonkers, Domino, Donkers
a.purrs // error because it's not a common field of Cat and Dog

let b: CatAndDog = {name: 'Domino', barks: true, purrs: true, wags: true}
b.name  // Domino
b.purrs // true
```

### Discriminating Unions
```typescript
type NetworkLoadingState = {
  state: "loading";
};
type NetworkFailedState = {
  state: "failed";
  code: number;
};
type NetworkSuccessState = {
  state: "success";
  response: {
    title: string;
    duration: number;
    summary: string;
  };
};
// Create a type which represents only one of the above types
// but you aren't sure which it is yet.
type NetworkState =
  | NetworkLoadingState
  | NetworkFailedState
  | NetworkSuccessState;
```
