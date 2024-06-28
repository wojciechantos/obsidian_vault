
`useState()` hook is a generic, so we should pass in the types that we expect. But on the other hand if we don't do that, TS is smart enough that it infers the type from the initial state value:

```ts
import { useState } from 'react';  
  
function Component() {  
    const [text, setText] = useState('shakeAndBake');  
    const [number, setNumber] = useState(1);  
  
    return (  
       <div>  
          <h2 className="mb-1">React & Typescript</h2>  
          <button 
	          className="btn btn-center" 
	          // if we set other param than string, TS error appears
	          onClick={() => setText('text')} 
	      >
			  click m
		  </button>  
          <button 
	          className="btn btn-center"
	          // if we set other param than number, TS error appears
	          onClick={() => setNumber(1)}
	      >
		      click me
		  </button>  
       </div>  
    );  
}  
  
export default Component;
```

but of course there are instances where we need to explicitly provide the type for the value and it will automatically set it for the `set` function. Here is an example with arrays:

```ts
import { useState } from 'react';  
  
function Component() {  
    const [list, setList] = useState<string[]>([]);  
  
    return (  
       <div>  
          <h2 className="mb-1">React & Typescript</h2>  
          <button  
             className="btn btn-center"
             onClick={() => setList(['string', 'another one'])}
             // this will cause an error (passing wrong type values)
             // onClick={() => setList([1, 2])}  
          >  
             click me  
          </button>  
       </div>  
    );  
}  
  
export default Component;
```

---

### Type inference

When TS infers some type automatically it infers in based on the provided value. Consider this example:

```ts
import { useState } from 'react';  
  
const navLinks = [  
    { id: 1, url: 'some url', text: 'some text' },  
    { id: 2, url: 'some url', text: 'some text' },  
    { id: 3, url: 'some url', text: 'some text' }  
];  
  
function Component() {
// here we pass navLinks as initial value of useState, so TS infers the array 
// element type as a shape:
// const navLinks: { id: number, url: string, text: string }[]  
    const [links, setLinks] = useState(navLinks); 
  
    return (  
       <div>  
          <h2 className="mb-1">React & Typescript</h2>  
          <button  
             className="btn btn-center"  
             onClick={() => {  
	            // here TS throws an error because 'text' is missing
                setLinks([...links, { id: 4, url: 'url' }]);  
             }}  
          >  
             click me  
          </button>  
       </div>  
    );  
}  
  
export default Component;
```

thats why type inference is not always a good solution. Although if one of the elements from the initial passed navLinks array would miss the prop, f.e. text, like here:

```ts
const navLinks = [  
    { id: 1, url: 'some url', text: 'some text' },  
    { id: 2, url: 'some url', text: 'some text' },  
    { id: 3, url: 'some url' }  
]; 
```

TS would see this as an optional prop, and the expected shape would look like this:

```ts
const navLinks: ({   id: number   url: string   text: string } | {   id: number   url: string   text?: undefined })[]
```

and the previously called setLinks with missing 'text' prop:

```ts
setLinks([...links, { id: 4, url: 'url' }]);
```

would be absolutely valid.

In order to be totally safe, we should do the following:

```ts
import { useState } from 'react';  
  
type Link = {  
    id: number, url: string, text?: string // we set the 'text' as optional 
};  
  
const navLinks: Link[] = [  // we annotate the type explicitly
    { id: 1, url: 'some url', text: 'some text' },  
    { id: 2, url: 'some url', text: 'some text' },  
    { id: 3, url: 'some url' }  
];  
  
function Component() {  
	// we pass the type to the generic
    const [links, setLinks] = useState<Link[]>(navLinks);  
  
    return (  
       <div>  
          <h2 className="mb-1">React & Typescript</h2>  
          <button  
             className="btn btn-center"  
             onClick={() => {  
	             // and here we can now safely pass the object without the                           optional property
                setLinks([...links, { id: 4, url: 'url' }]);  
             }}  
          >  
             click me  
          </button>  
       </div>  
    );  
}  
  
export default Component;
```