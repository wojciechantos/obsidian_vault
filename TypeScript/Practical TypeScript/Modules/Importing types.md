Preferably, we should define all our types in a separate `types.ts` file, to be able to access them in a various files.
To import type, we do this by adding export keyword to the type declaration:

```ts
// actions.ts

export type Student = {  
    name: string;  
    age: number;  
}
```

and we can either import them as usual:

``` ts
// function.ts

import { sayHello, person, Student } from './actions';
```

or by prefixing it with the `type` keyword, which btw suggests nicely, that the imported element is indeed a type:

``` ts
// function.ts

import { sayHello, person, type Student } from './actions';
```