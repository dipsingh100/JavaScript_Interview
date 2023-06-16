
# Day1

---

### Q1. Difference between “ == “ and “ === “ operators?
**Ans-** The "==" and "===" operators in JavaScript are used for comparison.  
== is used to compare two variables/values irrespective of the variable's data type. It compares the values on both sides and performs type coercion if necessary before making the comparison. This means that it converts the operands to a common type before comparing them. It is also called equality operator.
    
    console.log(5 == "5");  // true
    console.log(true == 1); // true
    console.log(null == undefined); // true

=== is used to compare two variables, but this will check strict type, which means it will check the datatype and compare two values. It compares the values on both sides without performing type coercion.

    console.log(5 === "5");  // false
    console.log(true === 1); // false
    console.log(null === undefined); // false

---

### Q2. What are the differences between var, let and const?
**Ans-** 	
- var declarations are globally scoped or function scoped while let and const are block scoped.
- var variables can be updated and re-declared within its scope 
- let variables can be updated but not re-declared
- const variables can neither be updated nor re-declared.
- Var variables are hoisted(move to the top we can access the variable before initializing and it will return undefined.)
- While var and let can be declared without being initialized, const must be initialized during declaration

---

### Q3. What is hoisting?
**Ans-** Hoisting is a behaviour in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed.  
only var variables are hosted for others it will through Reference Error(TDZ). 
    
    console.log(x); // Output: undefined
    var x = 10;
    console.log(x); // Output: 10

Similarly, function declarations are also hoisted. This means that we can call a function before its actual declaration in the code.

---

### Q4. What is a Temporal Dead Zone?
**Ans-**  The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs when variables declared with let and const are accessed before they are Declared or initialized. During the TDZ, accessing the variable will result in a ReferenceError and stops the further execution.  
To avoid the TDZ, it is recommended to declare variables at the top of the block scope, before they are accessed or used.

    console.log(x); // Throws a ReferenceError
    let x = 10;

---

### Q5. What is execution context?
**Ans-** Execution context in JavaScript refers to the environment in which a piece of code is executed.
There are two types of execution contexts: global Execution Context and function Execution Context. 
The global execution context is created when a JavaScript script first starts to run, and it represents the global scope in JavaScript.  
A function execution context is created whenever a function is called, representing the function's local scope.  
Execution Context is divided into two phases –
- Memory Allocation – Allocate the memory to the variables and functions 
- Code Execution – Executes the code line by line. 

---

### Q8. What are callbacks?
**Ans-** A callback is a function that is passed as an argument to another function and is called or executed inside that function. The purpose of using callbacks is to enable asynchronous and event-driven programming.  
Ex. –

    setTimout(sum(3,5),2000)
    Function sum(a,b){
    Console.log(a+b)
    }

Here the function sum is a callback function.

---

### Q9. What is meant by first class functions?
**Ans-** Assigning a function to a variable is first class function.

    Let p = function Sum(a,b){
    Return a+b;
    }
    console.log(P(1,5))  //Output: 6

---

### Q11. What are pure functions?
**Ans-** Pure functions are functions that always produce the same output given the same inputs every time the function called. 

    function add(a, b) {
        return a + b;
    }

The add function is a pure function because it takes two input parameters, a and b, and it consistently produces the same result for the same inputs
