
Tags: [[TypeScript]]

---
 
Enums in TS allow us to define a set of named constants. Using enums can make it easier to document intent, or create a set of distinct cases.

```ts
enum ServerResponseStatus {  
    Success = 200,  
    Error = 'Error',  
}  
  
interface ServerResponse {  
    result:  ServerResponseStatus;  
    data: string[];  
}  
  
function getServerResponse(): ServerResponse {  
    return {  
        result: ServerResponseStatus.Success,  
        data: ['first item', 'second item'],  
    }  
}  
  
const response = getServerResponse();  
console.log(response) // { result: 200, data: data: ['first item', 'second item'] }
```

---

```ts
enum ServerResponseStatus {  
    Success = 200,  
    Error = 'Error',  
}  
  
interface ServerResponse {  
    result:  ServerResponseStatus;  
    data: string[];  
}  
  
function getServerResponse(): ServerResponse {  
    return {  
        result: ServerResponseStatus.Error,  
        data: [],  
    }  
}  
  
const response = getServerResponse();  
console.log(response) // { result: 'Error', data: [] }
```

---
### Reverse mapping

In a numeric enum, TypeScript creates a reverse mapping from the numeric values to the enum member names. This means that if you assign a numeric value to an enum member, you can use that numeric value anywhere the enum type is expected.  
  
In a string enum, TypeScript does not create a reverse mapping. This means that if you assign a string value to an enum member, you cannot use that string value anywhere the enum type is expected. You must use the enum member itself.  
  
```ts  
enum ServerResponseStatus {  
  Success = 'Success',  
  Error = 'Error',  
}  
  
Object.values(ServerResponseStatus).forEach((value) => {  
  console.log(value);  
});  
```  
  
```ts  
enum ServerResponseStatus {  
  Success = 200,  
  Error = 500,  
}  
  
Object.values(ServerResponseStatus).forEach((value) => {  
  if (typeof value === 'number') {  
    console.log(value);  
  }  
});  
```  
  
```ts  
enum NumericEnum {  
  Member = 1,  
}  
  
enum StringEnum {  
  Member = 'Value',  
}  
  
let numericEnumValue: NumericEnum = 1; // This is allowed  
console.log(numericEnumValue); // 1  
  
let stringEnumValue: StringEnum = 'Value'; // This is not allowed  
```  
  
```ts  
enum ServerResponseStatus {  
  Success = 'Success',  
  Error = 'Error',  
}  
  
function getServerResponse(): ServerResponse {  
  return {  
    // result: ServerResponseStatus.Success,  
    // this will not fly with string enum but ok with number  
    result: 'Success',  
    data: ['first item', 'second item'],  
  };  
}  
```

---

### Practical example

```ts
enum UserRole {  
    Admin,  
    Manager,  
    Employee  
}  
  
type User = {  
    id: number,  
    name: string,  
    role: UserRole,  
    contact: [string, string],  
}  
  
function createUser(user: User): User {  
    return user;  
}  
  
const employee: User = {  
    id: 1,  
    name: "John Doe",  
    role: UserRole.Employee,  
    contact: ["john.doe@example.com", "1234567890"]  
}  
  
const result = createUser(employee);  
  
console.log(result); // {id: 1, name: 'John Doe', role: 2, contact: Array(2)}
```