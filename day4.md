# Day4

---

### Q1. What are function constructors?
**Ans-** In JavaScript, function constructors are a way to create objects using a constructor function. A constructor function is a regular JavaScript function that is used with the new keyword to create instances of objects.
The purpose of function constructors is to define a blueprint or template for creating multiple objects with similar properties and methods.  
Function constructors can also have methods defined within them, which will be shared among all instances of the objects created using the constructor.   

    function Person(name, age) {
    this.name = name;
    this.age = age;
    }

    // Creating instances of Person using the constructor
    var person1 = new Person('John', 30);
    var person2 = new Person('Jane', 25);

    console.log(person1.name); // Output: John
    console.log(person2.age); // Output: 25

---

### Q2. Explain call(), apply() and, bind() methods. Give an example of call(), apply(), bind()?
**Ans-**
1.	**Call -** The call() method is a predefined JavaScript method.
The call() method calls a function by passing this and specified values as arguments. With call(), an object can use a method belonging to another object.  

        const person = {
        fullName: function(city, country) {
            return this.firstName + " " + this.lastName + "," + city + "," + country;
        }
        }

        const person1 = {
        firstName:"John",
        lastName: "Doe"
        }

        person.fullName.call(person1, "Oslo", "Norway");


2.	**Apply -** The apply() method calls a function with the passed this keyword value and arguments provided in the form of an array. The apply() method takes arguments as an array.   

        const person = {
        fullName: function(city, country) {
            return this.firstName + " " + this.lastName + "," + city + "," + country;
        }
        }

        const person1 = {
        firstName:"John",
        lastName: "Doe"
        }

        person.fullName.apply(person1, ["Oslo", "Norway"]);


3.	**Bind -** The bind() method allows an object to borrow a method from another object without copying.
the bind() method has to be used to prevent losing this. Return the function and we can store that into any variable.

        const person = {
        firstName:"John",
        lastName: "Doe",
        fullName: function () {
            return this.firstName + " " + this.lastName;
        }
        }

        const member = {
        firstName:"Hege",
        lastName: "Nilsen",
        }

        let fullName = person.fullName.bind(member);


---

### Q3. What is the purpose of async/await keywords?
**Ans-**The purpose of async/await is to simplify the handling of Promises and make asynchronous code look more synchronous and linear. It avoids the need for excessive .then() chaining   

1.	 **Async Functions:** When you declare a function with the async keyword, it becomes an asynchronous function. Async functions always return a Promise, which resolves with the value returned by the function or rejects with an error thrown inside the function.
2.	**Await Operator:** The await keyword can only be used inside an asynchronous function. It allows you to pause the execution of the function until a Promise is resolved. The await keyword waits for the Promise to settle and then resumes the function, providing the resolved value of the Promise.   

        async function processData() {
        try {
            const result = await fetchData();
            // Perform operations on the fetched data
            console.log('Processed data:', result);
        } catch (error) {
            // Handle any errors that occurred during data processing
            console.error('Error while processing data:', error);
        }
        }

        processData();


---

### Q4. Explain prototypes?
**Ans-** Prototypes are a fundamental concept in JavaScript that allows objects to inherit properties and methods from other objects. Every object in JavaScript has an associated prototype, which serves as a blueprint for creating new objects or extending existing ones. The JavaScript prototype property allows us to add new properties and methods to object constructors:   

    function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
    }
    Person.prototype.nationality = "English";
    Person.prototype.name = function() {
    return this.firstName + " " + this.lastName;
    };
    // Create Object Instances
    var person1 = new Person ('John', ‘Jane’, 24, ‘blue’);
    // Access Prototype Method
    person1.name (); // Output: John Jane


---

### Q5. What is prototype chain?
**Ans-** In JavaScript, objects can have a prototype chain, where each object has a reference to its prototype, and the prototype itself can have its own prototype, forming a chain-like structure. This chain continues until reaching the top-level object, usually Object.prototype, which is the ultimate prototype in JavaScript.   
When accessing a property or method on an object, JavaScript first checks if the object itself has that property or method. If not found, it traverses up the prototype chain and checks the next prototype until it finds the desired property or reaches the end of the chain.   

    const GFather = {
        SayHello : function(){
            console.log("Hey Grand Father!!");
        }
    }
    
    const Father = Object.create(GFather);
    Father.Hello = function(){
        console.log("Say Hi to Father!!");
    }
    
    const Son = Object.create(Father);
    Son.Hi = function(){
        console.log("Hii I'm Son!!");
    }
    
    Son.SayHello()

When Son.SayHello() is called, it checks if the Son object has a SayHello method. Since it doesn't, it looks up the prototype chain and finds the SayHello method in the GFather object. The method is then executed, and the output "Hey Grand Father!!" is logged to the console.

---

### Q6. Give an example of inheritance using function constructor?
**Ans-**  

    function Person(first, last) {
    this.firstName = first;
    this.lastName = last;

    }

    function personHasCar(first, last, car){
    Person.call(this,first, last)
    this.car = car;
    }

    var person1 = new personHasCar("Robert","Downey","BMW")

    console.log(person1); 

In the above example we have created an instance of personHasCar Object that inherits the properties of Person Object. here we have used the call method inside the personHasCar object to call the current object by passing this and specified values as arguments of another object. 