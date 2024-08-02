
Tags: [[TypeScript]]

---
 
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

```ts
type Student = {  
    name: string;  
    study: () => void;  
};  
  
type User = {  
    name: string;  
    login: () => void;  
};  
  
type Person = Student | User;  
  
const randomPerson = (): Person => {  
    return Math.random() > 0.5  
       ? { name: 'john', study: () => console.log('Studying') }  
       : { name: 'mary', login: () => console.log('Logging in') };  
};  
  
const person = randomPerson();  
  
function isStudent(person: Person): person is Student {  
    // return 'study' in person;  // below we also check if the method is not                                         udefined
    return (person as Student).study !== undefined;
}  
  
if (isStudent(person)) {  
    person.study();  
} else {  
    person.login();  
}
```