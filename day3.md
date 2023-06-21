
# Day3

---

### Q1. What are promises and why do we need them?
**Ans-** Promises are object in JavaScript that provides a more elegant and structured way to handle asynchronous operations. The Promise object represents the completion and failure of an asynchronous operation. and allow us to write asynchronous code that is more readable, maintainable. They make it easier to handle errors using then and catch.   

The promise object has 3 states
- pending
- Fulfilled 
- rejected 

Here are some key reasons why promises are useful:   
**Improved Readability:** Promises use a chaining syntax that allows for a more sequential and readable code flow.   
**Error Handling:** Promises have built-in error handling mechanisms. They allow us to handle both synchronous and asynchronous errors in a centralized manner using the .catch() method.   
**Asynchronous Control Flow:** Promises provide better control over the flow of asynchronous operations. By chaining promises together using methods like .then()  
**Avoiding Callback Hell:** Promises help alleviate the problem of callback hell, which is the excessive nesting of callbacks in asynchronous code.


---

### Q2. What is promise chaining?
**Ans-** Promise chaining refers to the practice of chaining multiple asynchronous operations together using promises. It allows us to write sequential and readable code when dealing with asynchronous tasks.   

In promise chaining, each asynchronous operation returns a promise, which can be followed by the .then() method to specify the next operation to be performed after the completion of the current one. The .then() method takes a callback function as an argument, which will be executed when the promise is fulfilled

    asyncOperation1()
    .then(result1 => {
        // Perform some operation with result1
        return asyncOperation2(result1);
    })
    .then(result2 => {
        // Perform some operation with result2
        return asyncOperation3(result2);
    })
    .then(result3 => {
        // Perform some operation with result3
        console.log("Final result:", result3);
    })
    .catch(error => {
        // Handle any errors that occurred during the promise chain
        console.error("An error occurred:", error);
    });


---

### Q3. What is the DOM?
**Ans-** DOM stands for Document Object Model. It is a programming interface for web documents, representing the structure of an HTML or XML document as a tree-like model. The DOM provides methods and properties that allow developers to dynamically access, manipulate, and update the content, structure, and style of web documents.

---

### Q4. What are closures? Give an example of closure
**Ans-** In JavaScript, a closure is a combination of a function and its lexical environment. It allows a function to access variables from its outer (enclosing) scope even after the outer function has finished executing.

    function outerFunction() {
    var counter = 0;

    function innerFunction() {
        return counter+=1
    }

    return innerFunction;
    }

    var closure = outerFunction();
    closure(); 
    closure();
    closure(); //counter is 3 now


---

### Q5. How many operators do we have in JS ?
**Ans-** 
- **Arithmetic Operators:** These operators are used for performing arithmetic operations on numbers. Examples include + (addition), - (subtraction), * (multiplication), / (division), % (remainder), ++ (increment), and -- (decrement).
- **Assignment Operators:** These operators are used to assign values to variables. Examples include = (simple assignment), += (addition assignment), -=, *=, /=, and %= (compound assignment operators).
- **Comparison Operators:** These operators are used to compare values and determine their relationship. Examples include == (equality), === (strict equality), != (inequality), !== (strict inequality), > (greater than), < (less than), >= (greater than or equal to), and <= (less than or equal to).
- **Logical Operators:** These operators are used to perform logical operations on boolean values. Examples include && (logical AND), || (logical OR), and ! (logical NOT).
- **Bitwise Operators:** These operators are used to perform bitwise operations on binary representations of numbers. Examples include & (bitwise AND), | (bitwise OR), ^ (bitwise XOR), ~ (bitwise NOT), << (left shift), >> (right shift), and >>> (zero-fill right shift).


---

### Q6. What are objects in javascript?
**Ans-** In JavaScript, objects are composite data types that allow you to store and manipulate collections of key-value pairs.

    var person = {
    name: 'John',
    age: 30,
    occupation: 'Developer'
    };

In the example above, person is an object with three properties: name, age, and occupation. Each property has a key (or name) and a corresponding value.

Objects in JavaScript are mutable, which means you can add, modify, or delete properties dynamically:
Objects can also contain methods, which are functions assigned as property values.


