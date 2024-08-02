
Tags: [[React]] [[TypeScript]]

---
 
Example:

```ts
import React, { useState } from 'react';  
  
function Component() {  
    const [text, setText] = useState('');  
    const [email, setEmail] = useState('');
    // here we need to pass the generic type for the 'change' event with the            extension for the input element
    const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {  
       console.log(e.target.value);  
       setEmail(e.target.value);  
    };  
  
    return (  
       <section>  
          <h2>Events example</h2>  
          <form className="form">  
             <input  
				name="text"  
			    type="text"  
			    className="form-input mb-1"  
			    value={text}  
			    onChange={(e) => setText(e.target.value)}  
			/>  
			<input  
			    name="email"  
			    type="email"  
			    className="form-input mb-1"  
			    value={email}  
			    onChange={handleChange}  
			/>  
            <button type="submit" className="btn btn-block">submit</button>  
          </form>  
       </section>  
    );  
}  
  
export default Component;
```

### Form events - submit

```ts
import React, { useState } from 'react';  
  
function Component() {  
    const [text, setText] = useState('');  
    const [email, setEmail] = useState('');  
    const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {  
       setEmail(e.target.value);  
    };  
  
    const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {  
       e.preventDefault();  
       const formData = new FormData(e.currentTarget);  
  
       const data = Object.fromEntries(formData);  
       console.log(data);  
    };  
  
    return (  
       <section>  
          <h2>Events example</h2>  
          <form onSubmit={handleSubmit} className="form">  
             <input  
                name="text"  
                type="text"  
                className="form-input mb-1"  
                value={text}  
                onChange={(e) => setText(e.target.value)}  
             />  
             <input  
                name="email"  
                type="email"  
                className="form-input mb-1"  
                value={email}  
                onChange={handleChange}  
             />  
             <button type="submit" className="btn btn-block">submit</button>  
          </form>  
       </section>  
    );  
}  
  
export default Component;
```

