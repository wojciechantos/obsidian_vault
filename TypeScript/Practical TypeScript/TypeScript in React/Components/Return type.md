In most part TS will infer the React.JSX (JSX.Element before) type, so we usually don't need to annotate the type. 

```ts
function Component() {  
  return (  
    <div>  
      <h2>React & Typescript</h2>  
      <h2>Return Type</h2>  
    </div>  
  );  
}  
export default Component;
```

But of course we can explicitly set the types that can be returned:

```ts
import React from 'react';  
  
function Component(): string | null | React.JSX {  
    // return 'string';  
    // return null;  return (  
    <div>  
      <h2>React & Typescript</h2>  
      <h2>Return Type</h2>  
    </div>  
  );  
}  
export default Component;
```