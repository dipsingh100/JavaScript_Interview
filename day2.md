# Day2

---

### Q1. What is Execution Context?
**Ans-** Execution context in JavaScript refers to the environment in which a piece of code is executed.   
There are two types of execution contexts:    
1. global Execution Context   
2. function Execution Context.  

The global execution context is created when a JavaScript script first starts to run, and it represents the global scope in JavaScript.  
A function execution context is created whenever a function is called, representing the function's local scope.   
Execution Context is divided into two phases –
**Memory Allocation** – Allocate the memory to the variables and functions   
**Code Execution** – Executes the code line by line. 


---

### Q2. What is an Event Loop and Call Stack?
**Ans-** The event loop and call stack are core components of JavaScript's runtime environment, working together to manage the execution of code and handle asynchronous operations.
1.	*Call Stack*: The call stack is a data structure that keeps track of function calls in the JavaScript code. It follows a Last-In-First-Out (LIFO) order, meaning the most recently executed function is at the top of the stack. Whenever a function is invoked, a new frame is pushed onto the stack, representing that function's execution context. As the function completes, its frame is popped off the stack, and the control returns to the previous frame.
The call stack operates synchronously, executing functions in a sequential manner. It ensures that functions are executed in the order they are called and maintains the correct execution context.
2.	*Event Loop*: The event loop is responsible for handling asynchronous operations in JavaScript, such as timers, AJAX requests, and callbacks. It constantly checks for pending tasks and executes them when appropriate.   
When an asynchronous operation is encountered, it is offloaded to the browser or runtime environment, which handles it independently. Once the asynchronous task completes, it is placed in a task queue (also known as the "callback queue").   
The event loop monitors the call stack and the task queue. If the call stack is empty, it takes the next task from the queue and pushes it onto the call stack, initiating its execution


---

### Q3. What is creation phase and execution phase?
**Ans-** In JavaScript, the process of executing a script involves two main phases: the creation phase (also known as the initialization phase) and the execution phase.
1.	*Creation Phase*:
During the creation phase, the JavaScript engine performs the following tasks:
-	Creates the global execution context and pushes it onto the call stack.
-	Hoists function declarations and variable declarations to the top of their respective scopes.
-	Initializes variables to undefined and allocates memory for function declarations.
2.	*Execution Phase*: Once the creation phase is completed, the JavaScript engine moves to the execution phase. In this phase, it starts executing the code line by line, following the program flow and evaluating expressions.  
During the execution phase, the JavaScript engine performs the following tasks:
-	Executes the code within each execution context in the order in which it appears in the program.
-	Assigns values to variables, executes function invocations, performs mathematical calculations, evaluates conditions, and executes other statements.
-	Manages the call stack, pushing new execution contexts onto the stack when entering a function and popping them off the stack when a function completes execution.
-	Handles asynchronous operations such as timers, event handlers, and AJAX requests by adding them to the appropriate event queues and executing them when their turn comes.  
-	Manages the scope chain to resolve variable and function references.

---

### Q4. What is the spread operator?
**Ans-** The spread operator, denoted by ..., is a powerful feature introduced in ECMAScript 6 (ES6) that allows an iterable, such as an array or a string, to be expanded into individual elements. It provides an easy and concise way to manipulate arrays, objects, and function arguments. It is used for 
- Array deep Copy   
    
        const originalArray = [1, 2, 3];
        const copiedArray = [...originalArray]; // [1, 2, 3]

- In Functions   

        function Sum(a,b,c){
            Return a+b+c
        }
        Sum(…[1,2,3])

- In Objects

        const obj1 ={
            name: "aditya",
            age: 24
        }
        const obj2 = {
            city:"Delhi",
            ...obj1
        }

---

### Q5. What is the use of setTimeout?
**Ans-** The setTimeout function in JavaScript is used to schedule the execution of a callback function after a specified delay (in milliseconds). It is commonly used to introduce a time delay in executing a specific block of code or to create timed intervals for executing functions.   
The general syntax of the setTimeout function is as follows:   

    setTimeout(callback, delay)

-  callback: The function to be executed after the specified delay.
-  delay: The time delay in milliseconds before executing the callback.


---

### Q6. What are callbacks?
**Ans-** A callback is a function that is passed as an argument to another function and is called or executed inside that function. The purpose of using callbacks is to enable asynchronous and event-driven programming.
Ex. – 

    setTimout(sum(3,5),2000)
    Function sum(a,b){
        Console.log(a+b)
    }
Here the function sum is a callback function.


---

### Q7. What is callback hell?
**Ans-** Callback hell, also known as the pyramid of doom, is a term used to describe a situation where code becomes nested and difficult to read and maintain due to excessive use of callback functions. It occurs when there are multiple tasks that depend on the results of each other. In call-back hell code grows horizontal, if one task fail then the whole pyramid breaks.

    // Code after operation1 completes
    asyncOperation2(result1, function(result2) {
        // Code after operation2 completes
        asyncOperation3(result2, function(result3) {
        // Code after operation3 completes
        // ...
        });
     });
    });

---

### Q8. Difference between undefined vs not defined vs  NaN?
**Ans-** 
1.	Undefined: Undefined is a primitive data type in JavaScript. It is a variable that has been declared but has not been assigned a value.   
For example: 

    let x; // variable declared but not assigned
    console.log(x); // undefined
    function foo() {
    // no return statement
    }
    console.log(foo()); // undefined

2.	Not Defined: "Not defined" is an error that occurs when we try to access a variable that has not been declared or is out of scope.  
For example: 
    
        console.log(y); // ReferenceError: y is not defined
        function bar() {
            console.log(z); // ReferenceError: z is not defined
        }
        bar();

3.	NaN: NaN stands for "Not a Number" and is a value of the Number data type in JavaScript. It is returned when a mathematical operation is performed, but the result is not a valid number.

        console.log(10 / "a"); // NaN
        console.log(Math.sqrt(-1)); // NaN


---
