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

### Differences between Type and Interface

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


