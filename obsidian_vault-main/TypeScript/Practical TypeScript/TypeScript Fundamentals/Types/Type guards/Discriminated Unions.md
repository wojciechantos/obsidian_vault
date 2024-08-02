
Tags: [[TypeScript]]

---
 
A discriminated union in TS is a type that can be one of several different types, each identified by a unique literal property (the discriminator), allowing for type-safe handling of each possible variant.

```ts
type IncrementAction = {  
    type: 'increment',  
    amount: number;  
    timestamp: number;  
    user: string;  
};  
  
type DecrementAction = {  
    type: 'decrement',  
    amount: number;  
    timestamp: number;  
    user: string;  
};  
  
type Action = IncrementAction | DecrementAction;  
  
function reducer(state: number, action: Action) {  
    switch (action.type) {  
       case 'increment':  
          return state + action.amount;  
       case 'decrement':  
          return state - action.amount;  
       default:  
          const unexpectedAction: never = action;  
          throw new Error(`Unexpected action: ${unexpectedAction}`);  
    }  
}  
  
const newState = reducer(15, {  
    type: 'increment',  
    user: 'john',  
    amount: 5,  
    timestamp: 123456  
});
```