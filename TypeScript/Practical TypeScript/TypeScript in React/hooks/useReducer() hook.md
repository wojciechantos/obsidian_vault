
Taken from the course example.

(reducer.ts)
```ts
export type CounterState = {  
    count: number,  
    status: string,  
}  
  
export const initialState: CounterState = {  
    count: 0,  
    status: 'pending',  
}  
  
type UpdateCountAction = {  
    type: 'increment' | 'decrement' | 'reset',  
}  
  
type SetStatusAction = {  
    type: 'setStatus';  
    payload: 'active' | 'inactive';  
};  
  
type CounterAction = UpdateCountAction | SetStatusAction;  
  
export const counterReducer = (state: CounterState, action: CounterAction): CounterState => {  
    switch (action.type) {  
       case 'increment':  
          return { ...state, count: state.count + 1 };  
       case 'decrement':  
          return { ...state, count: state.count - 1 };  
       case 'reset':  
          return { ...state, count: 0 }  
       case 'setStatus':  
          return { ...state, status: action.payload };  
       default:  
          const unhandledActionType: never = action;  
          throw new Error(`Unhandled action type: ${unhandledActionType}. Please           double check the counter reducer`);  
    }  
};
```

(index.tsx)
```ts
import { useReducer } from 'react';  
import { initialState, counterReducer } from './reducer.ts';  
  
function Component() {  
    const [state, dispatch] = useReducer(counterReducer, initialState);  
    return (  
        <div>  
            <h2>Count: {state.count}</h2>  
            <h2>Status: {state.status}</h2>  
  
            <div className='btn-container'>  
                <button 
	                onClick={() => dispatch({type: 'increment'})}
	                className='btn'
	            >  
	                    Increment  
                </button>  
                <button 
	                onClick={() => dispatch({type: 'decrement'})}
	                className='btn'
	            >  
                    Decrement  
                </button>  
                <button 
	                onClick={() => dispatch({type: 'reset'})} 
	                className='btn'
	            >  
		            Reset  
                </button>  
            </div>  
            <div className='btn-container'>  
                <button  
                    onClick={() => dispatch(
	                    { 
		                    type: 'setStatus', 
		                    payload: 'active'
		                }
		            )}  
                    className='btn'  
                >  
                    Set Status to Active  
                </button>  
                <button  
                    className='btn'  
                    onClick={() => dispatch(
	                    { 
		                    type: 'setStatus', 
		                    payload: 'inactive'
		                }
		            )}  
                >  
                    Set Status to Inactive  
                </button>  
            </div>  
        </div>  
    );  
}  
  
export default Component
```