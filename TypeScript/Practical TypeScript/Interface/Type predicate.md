```ts
interface Person {  
    name: string;  
}  
  
interface DogOwner extends Person {  
    dogName: string;  
}  
  
interface Manager extends Person {  
    managePeople(): void,  
    delegateTasks(): void,  
}  
  
type PersonType = Person | DogOwner | Manager;  
  
function getEmployee(): PersonType {  
    const random = Math.random();  
  
    if(random < 0.33) {  
        return {  
            name: 'john'  
        };  
  
    } else if(random < 0.66) {  
        return {  
            name: 'sarah',  
            dogName: 'rex'  
        };  
    } else {  
        return {  
            name: 'bob',  
            managePeople() {  
                console.log('Managing people...');  
            },  
            delegateTasks() {  
                console.log('Delegating tasks...');  
            },  
        };  
    }  
}  
  
const employee: PersonType = getEmployee();  

/* In order to be able to call the delegateTasks() method the isManager function return type needs to be specified like below */
function isManager(obj: PersonType): obj is Manager {  
    return 'managePeople' in obj;  
}  

/* Without annotating it like above and assigning a boolean return type for example, the TS would call an error, that there is no access to the delegateTasks() method*/
if (isManager(employee)) {  
    employee.delegateTasks();  
}
```