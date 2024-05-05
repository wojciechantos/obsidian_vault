An error is a type of object built into the JS language, consisting of a name/type and a message.

---

The first part of an error displays the type of error, to give the first clue as to what to deal with.

![[Pasted image 20240408062228.png]]


--- 

**Stack trace** - it helps to understand when the error was thrown in the application, and what functions were called that led up to the error.

Example: 
```
const a = 5;
const b = 10;

function add() {
  return c;
}

function print() {
  add();
}

print();

```

The func `print()` should call on `add()`, which returns a variable named `c`, which currently has not been declared. The corresponding error as follows:

![[Pasted image 20240408063210.png]]

--- 

**Most common errors**

1.  [Syntax error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError) - thrown when the code is written incorrectly, f.e. the syntax is invalid
2.  [Reference error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError) - thrown when one refers to a variable that is not declared and/or initialized within the current scope.
3. [Type error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) - might be thrown for a few different reasons: 
	- an operand or argument passed to a function is incompatible with the type expected by that operator or function
	- when attempting to modify a value that cannot be changed
	- when attempting to use a value in an inappropriate way

--- 

**window.console object methods**

[Link](https://www.w3schools.com/jsref/obj_console.asp)
