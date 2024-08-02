
Tags: [[TypeScript]]

---
 
When the 'student' is created with the props passed to the function inline like this:

```ts
function createStudent(student: { id: number; name: string }): void {  
    console.log(`Welcome to the course ${student.name.toUpperCase()}!!!`);  
};
  
createStudent({ id: 3, name: 'Jared', email: 'jarjar@gmail.com' });
```

TypeScript will throw an error on property email. However, when we create the student like this:

```ts
function createStudent(student: { id: number; name: string }): void {  
    console.log(`Welcome to the course ${student.name.toUpperCase()}!!!`);  
};  
  
const newStudent = {  
    id: 3,  
    name: 'anna',
    email: 'anna@gmail.com' // notice the email prop is not annotated!
};  
  
createStudent(newStudent);
```

there will be no error. It happens because when the object is created inline like in the upper example, TypeScript assumes that we have full control over what we are passing as the params.
When we are referencing an object like in the second example, we do not always have the access to it, so TypeScript is not complaining and only checks the annotated props of a referenced object.