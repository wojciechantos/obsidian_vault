
Tags: [[TypeScript]]

---

```json
{  
  "compilerOptions": {  
    "target": "ES2020", // it controls the JS version output code
    "useDefineForClassFields": true,  
    "module": "ESNext", // it controls the module syntax output code
    "lib": ["ES2020", "DOM", "DOM.Iterable"], // controls the declaration files
    "skipLibCheck": true,  
  
    /* Bundler mode */  
    "moduleResolution": "bundler",  
    "allowImportingTsExtensions": true,  
    "resolveJsonModule": true,  
    "isolatedModules": true,  
    "noEmit": true,  
    "moduleDetection": "force",  
  
    /* Linting */  
    "strict": true, // flag that controls how the errors/warnings are displayed 
    "noUnusedLocals": true,  
    "noUnusedParameters": true,  
    "noFallthroughCasesInSwitch": true  
  },  
  "include": ["src"] // this indicates where TS are located 
}
```