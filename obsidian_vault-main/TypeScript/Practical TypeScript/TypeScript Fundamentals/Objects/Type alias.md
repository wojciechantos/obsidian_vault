
Tags: [[TypeScript]]

---

Type alias naming convention is that it starts with the upper case

```ts
type User = { id: number; name: string; isActive: boolean };  
  
const john: User = {  
    id: 1,  
    name: 'john',  
    isActive: true,  
};  
const susan: User = {  
    id: 1,  
    name: 'susan',  
    isActive: false,  
};  
  
function createUser(user: User): User {  
    console.log(`Hello there ${user.name.toUpperCase()} !!!`);  
  
    return user;  
}
```

---

```ts
type StringOrNumber = string | number;

let age: StringOrNumber = 20;
let age: StringOrNumber = 'young';


type Theme = 'light' | 'dark';  
  
let theme: Theme;  
  
theme = '<IDE will suggest one of available ones: dark or light>'  
theme = 'light';  
  
function setTheme(t: Theme): void {  
    theme = t;  
}  
  
setTheme('<IDE will suggest one of available ones: dark or light');
```

---

```ts
type Employee = {  
    id: number,  
    name: string,  
    department: string,  
}  
  
type Manager = {  
    id: number  
    name: string  
    employees: Employee[]  
}  
  
type Staff = Employee | Manager;  
  
const employee1: Employee = {  
    id: 1,  
    name: "John Doe",  
    department: "Sales",  
}  
  
const employee2: Employee = {  
    id: 2,  
    name: "Ed Sullivan",  
    department: "Logistics",  
}  
  
const employee3: Employee = {  
    id: 3,  
    name: "Maria Hawkins",  
    department: "Customer Service",  
}  
  
const manager: Manager = {  
    id: 1,  
    name: "Jane Smith",  
    employees: [employee1, employee2, employee3]  
}  
  
function printStaffDetails(staff: Staff): void {  
    if('employees' in staff) {  
        console.log(`${staff.name} is a manager for ${staff.employees.length} employees`);  
    } else {  
        console.log(`${staff.name} is an employee in the ${staff.department} department`);  
    }  
}  
  
console.log(printStaffDetails(employee1));  
console.log(printStaffDetails(employee2));  
console.log(printStaffDetails(employee3));  
console.log(printStaffDetails(manager));
```

### Computed properties

```ts
const propName = 'age'  
  
type Animal = {  
    [propName]: number;  
}  
  
let tiger = { [propName]: 5 };
```