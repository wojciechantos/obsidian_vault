Type Script by default treats files as scripts in the global scope, so declaring a variable with the same name in two separate files will throw an error, that the variable is already declared.

```ts
// file1.ts
const susan = 'susan' // Error: the variable 'susan' is already declared
```

and in a separate non-module file:
```ts
// file2.ts
const susan = 'susan' // Error: the variable 'susan' is already declared
```


To change the default behavior there are few options:

#1 Adding import or export statement anywhere in the file, TS will immediately treat the file as a module and the error is no longer present.

#2 In the `tsconfig.json` - `compilerOptions` object we can add the 
`"moduleDetection": "force"` directive.

---

### JS files

When you set `"allowJs": true` in your `tsconfig.json`, TypeScript will process JavaScript files and can infer types to a certain extent based on the structure and usage of your JavaScript code.  
  
However, TypeScript's ability to infer types from JavaScript is not as robust as when working with TypeScript files. For example, it might not be able to infer complex types or types that depend on runtime behavior.  
  
```ts  
  "allowJs": true,  
```