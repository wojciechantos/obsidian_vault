
Tags: [[TypeScript]]

---
## Build time, not run time!

Although TypeScript will not crash while development even if the types are wrongly declared it will not allow to pass tsc checks. So if the application needs to be build (to be able to ship to production) the TypeScript errors need to be resolved first.

For example if the app is built with Vite, the following package.json build command first initiates the typescript compiler which will throw errors if any made:

```ts
"scripts": {  
  "dev": "vite",  
  "build": "tsc && vite build",  
  "preview": "vite preview"  
},
```

---

## Differences between Type and Interface

- Type aliases can represent primitive types:
```ts
type Score = number;
type NumberOrString = number | string;
```

or literal types:
```ts
type Direction = 'up' | 'down' | 'left' | 'right';
```

- Interfaces are primarily used to represent the shape of an object and cannot represent primitives or literals.
- Interfaces can be merged using declaration merging. If defined with the same name more than once, TS will merge their definitions. Type aliases cannot be merged in this way.
- Interfaces can be used with classes, Type Aliases cannot.


---

## Non-null assertion operator

Because TS is compiled in build time, querying html elements requires checking if the queried element is for sure present and is not null or undefined. One way to do so is the "?" operator:

```ts
const btn = document.querySelector('.btn');

btn?.addEventListener('click', (e) => {});

/* or, but less common:
if (btn) {  
  // do something  
}
*/


```

In the example above, without placing the "?" operator the compilation would be unsuccessful, because TS assumes that for example because of mistyping class name the queried button can be null, so we would not be able to set the event listener.

Other way to avoid this is by using the "!" operator. In TS it is known as non-null assertion operator. It is used to declare, that it's preceding expression is not null or undefined.

```ts
const btn = document.querySelector('.btn')!;
```
