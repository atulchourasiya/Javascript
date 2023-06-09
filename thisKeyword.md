# What is this keyword
  
  In JavaScript, the this keyword refers to the context in which a function is executed. It allows you to access and manipulate properties and methods within that context. The value of this is determined dynamically at runtime, based on how a function is invoked.

## Global this
  When this is used in the global scope (outside of any function), it refers to the global object. In a web browser environment, the global object is typically window.
javascript
 ```
console.log(this); // Output: [object Window] (in a web browser) 
```
## Object this 
When a function is invoked as a method of an object, this refers to the object itself.
```
var person = {
  name: 'John',
  greet: function() {
    console.log('Hello, ' + this.name);
  }
};

person.greet(); // Output: Hello, John
```
## Constructor Function
When a function is used as a constructor function (invoked with the new keyword), this refers to the newly created instance of the object.
```
function Person(name) {
  this.name = name;
}

var john = new Person('John');
console.log(john.name); // Output: John
```
Here, this inside the Person constructor function refers to the newly created object john.

## Explicit Binding
You can also explicitly set the value of this using methods like call(), apply(), or bind().
```
function greet() {
  console.log('Hello, ' + this.name);
}

var person = {
  name: 'John'
};

greet.call(person); // Output: Hello, John
```
In this example, call() is used to invoke the greet function with this explicitly set to the person object.

It's important to note that the value of this is not determined by how or where a function is defined, but by how it is invoked. Understanding the context in which a function is executed and how this behaves in different scenarios is crucial for writing effective JavaScript code.
