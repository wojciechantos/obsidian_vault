
### Inline

```ts
function Component({ name, id }: { name: string; id: number }) {  
  return (  
    <div>  
      <h1>Name: {name}</h1>  
      <h2>ID: {id}</h2>  
    </div>  
  );  
}  
export default Component;
```

---

### Type Alias / Interface

We can either use type or interface, depends on preference.

```ts
type ComponentProps = {  
    name: string;  
    id: number  
};  
  
// interface ComponentProps {  
//     name: string;  
//     id: number;  
// }  
  
function Component({ name, id }: ComponentProps ) {  
  return (  
    <div>  
      <h1>Name: {name}</h1>  
      <h2>ID: {id}</h2>  
    </div>  
  );  
}  
  
export default Component;
```

---

### Children prop

Note in the example above, that `children` prop is optional! It prevents errors, because some components might not need any children to be rendered.

```ts
import React from 'react';  
  
type ComponentProps = {  
    name: string;  
    id: number  
    children?: React.ReactNode
};  
  
function Component({ name, id, children }: ComponentProps ) {  
  return (  
    <div>  
      <h1>Name: {name}</h1>  
      <h2>ID: {id}</h2>  
        {children}  
    </div>  
  );  
}  
  
export default Component;
```

like here:

```ts
import Component from './starter/02-props';  
  
function App() {  
  return (  
    <main>  
        <Component name='peter' id={123}>  
            <h2>child element</h2>  
        </Component>  
        <Component name='john' id={456} />  
    </main>  
  );  
}  
  
export default App;
```

#### There is also another option - `PropsWithChildren`

It basically means that we import the PropsWithChildren type declaration from React. Because PropsWithChildren is a generic as described in the definition file: 

```ts
type PropsWithChildren<P = unknown> = P & { children?: ReactNode | undefined };
```

anything that we pass in to the generic as argument will be then merged with the provided object. So we can pass into the generic brackets `<>` the shape of the props object like this:

```ts
import { type PropsWithChildren }from 'react';  
  
type ComponentProps = PropsWithChildren<{  
    name: string;  
    id: number  
}>;  
  
function Component({ name, id, children }: ComponentProps ) {  
  return (  
    <div>  
      <h1>Name: {name}</h1>  
      <h2>ID: {id}</h2>  
        {children}  
    </div>  
  );  
}  
  
export default Component;
```