In TypeScript, .d.ts files, also known as declaration files, consist of type definitions, and are used to provide types for JavaScript code. They allow TypeScript to understand the shape and types of objects, functions, classes, etc., in JavaScript libraries, enabling type checking and autocompletion in TypeScript code that uses these libraries.  
  
In `tsconfig.json` 'lib' is set to `["ES2020", "DOM", "DOM.Iterable"]`. This specifies the library files to be included in the compilation.  

A repo with a LOT of type declaration files to download:
[DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped)  

#### Example

Password hashing library:
  
```sh  
npm i bcryptjs  
```  

but the types declaration is not included with the lib, so we need to install it, so TS will be aware of them and will have an access to them.

(always install type declarations with --save-dev!)
```sh  
npm install --save-dev @types/bcryptjs  
```