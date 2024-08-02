
Tags: [[TypeScript]]

---

If we are setting the event listener and we set up the logic directly in the callback function like this:

```ts
taskForm.addEventListener('submit', (event) => {  
    event.preventDefault();  
    const taskDescription = formInput.value;  
    if (taskDescription) {  
       console.log(taskDescription);  
  
       formInput.value = '';  
       return;  
    }  
    alert('please add the task description');  
});
```

event will have the correct type and it will be all good. But if we set up the callback function as a reference like this:

```ts
function createTask(event: SubmitEvent) {  // here we must set the type!
    event.preventDefault();  
    const taskDescription = formInput.value;  
    if (taskDescription) {  
       console.log(taskDescription);  
  
       formInput.value = '';  
       return;  
    }  
    alert('please add the task description');  
};  
  
taskForm.addEventListener('submit', createTask);
```

we need to explicitly set the type for the event param!