# **ES6**

!["javascript"](images/1.jpeg)
## **What is ES6 ?**

**ES6** is also known as **ECMAScript 6** and **ECMAScript 2015**. Some call it **JavaScript 6** and it is the latest version of ECMAScript standard for Javascript language published in june 2015. 

---
## **What is ES ?**
In the year 1996, a standards organization called **ECMA** *( European Computer Manufacturers Association )* **International** carved out standard specification called **ECMAScript (ES)**.

ECMAScript provides the rules, details, and guidelines that a scripting language must observe to be considered ECMAScript compliant.
ECMAScript was created to standardize JavaScript, to ensure the interoperability of web pages written using Javascript across different web browsers. 

The most well-known implementations of ECMAScript is Javascript. Moreover ActionScript (from Macromedia/Adobe Systems) and JScript (from Microsoft) are other implementations as well.  

---
## **Different Versions Of ECMAScript (ES)**
JavaScript is always evolving, and new features are released every year. Till date, ES has published **Nine versions** and the latest one (9th version) was published in the year 2018.

ES Versions| Year Released
:----:     | :----:   
ES1        | 1997
ES2        | 1998
ES3        | 1999
ES4        | Abandoned
ES5        | 2009
ES6        | 2015
ES7        | 2016
ES8        | 2017
ES9        | 2018

> The current ECMAScript version  supported in modern browsers is ES5. However, ES6 tackles most of the limitations of the core language, making it easier for developers to code.  

---
## **Difference Between Javascript & ECMAScript**
+ **Javascript** is a general purpose scripting language that conforms to the ECMAScript specification. whereas **ECMAScript** is the specification defined in ECMA-262 for creating a general purpose scripting language.

+ By reading the [ECMAScript specification](https://262.ecma-international.org/6.0/), one can learn how to create a scripting language like Javascript etc. whereas by reading the [JavaScript documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript), one can learn how to use a general purpose scripting language in an efficient way.

---
## **why Learn ES6 ?**
The **next generation** of Javascript is something known as **ES6**.
- ES6, released in 2015, added many new powerful features to the language.
- ES6 brings new syntax and new awesome features which enables the programmer to make code more modern, cleaner and readable.
- ES6 allows developers to write shorter and smarter code.

- As React uses ES6, so to get the maximum performance one should be familiar with some of the new features like:
Classes, Arrow Functions, Variables (let, const, var) etc.

---
## **ECMAScript(ES6) Features**

!["Javascript ES6 Features"](images/2.jpeg)

### **New Features in ES6**

Below is a list of the ES6 features that have upgraded the basic data types and data structures of Javascript :

>  * The Let & Const Keyword  
>  * Arrow Functions
>  * Default Parameter
>  * Rest Parameter
>  * Spread Operator
>  * Template Literal
>  * Destructuring
>  * Module
>  * Class
>  * promise
>  * Symbol
>  * Set Datastructure
>  * For/Of Loop
>  * Exponentiation Operator
>  * New Builtin Methods
>    * Array
>      * Array.find()
>      * Array.findIndex()
>      * Array.from()
>      * Array.fill()
>    * Strings
>      * String.startsWith()
>      * String.endsWith()
>      * String.includes()
>      * String.repeat()
>    * Object 
>      * Object.assign()  
          
See the [ES6 standard](https://262.ecma-international.org/6.0/) for full specification of the ECMAScript 6 language.

### **The Let & Const Keyword**
---
Before ES6 there was only `functional scope` and `global scope`, which were created using the var keyword.

The variables declared `globally` can be accessed from anywhere in javascript and the variables declared `locally` inside a function can only be accessed by the function itself and not globally.

The `let keyword` which is used to create *Block-Scoped* variables in javascript. 

Let keyword usage:
``` javascript
let a = 5 ;
var b = 9 ;
{ // block scope
    let a = 7 ;
    //Here a is 7
    //Here b is 9
}
//Here b is 9
//Here a is 5 
```
The `const keyword` has same properties as the let keyword including the *single-assignment* property which disables a const variable to be re-assigned new content.

Const keyword usage:
```javascript
var a = 8 ;
const b = 9 ; 
    {//Block scope
     //Here b is 9
     //Here a is 8
      const b = 1; //Here b is 1 
      b = 7 ;      //Error, assignment to const 
    }
     //Here b is 9
const a = 15 //Error, already declared 
let b = 10;  // Error, already declared 
```
The let and const behaves same when used with Objects as well as Arrays.

With Arrays:
```javascript
let a = [1, 2, 3]; 
const s = [5, 6, 7];
a = [4, 5, 6];
s = [1, 2, 3]; //Error, assignment to const 
s[2] = 9;
//Here s is [1, 2, 9]
//Here  a is [4, 5, 6]
```
However, In case of objects, `Object.freeze(objectName)` is used to prevent mutation it will restrict any changes made to the object.

With Objects:
```javascript
//Object.freeze() usage
let obj = {
  name:"objectMadeWithLet"
};
const obj1 = { 
  name:"objectMadeWithConst"
};

Object.freeze(obj);

obj.review = "don't get assigned";
//Doesn't work because its freezed

obj1.newProp = "get assigned";
//It works well

//Here obj is { name:"objectMadeWithLet" }

//Here obj1 is { name:"objectMadeWithConst", newProp = "get assigned" }
 
```

### **Arrow Functions**
---
`Arrow Functions` also called as *Fat Arrow Functions* uses `=>` to achieve the task. They are one liner functions similar to the Lambda functions in programming languages like Java 8 and Python.

In previous version of Javascript(ES5) `function` keyword was used to declare a function.

ES5 version usage:
```javascript
//Global function
function Square (a){
    console.log(a*a)
}
Square(9) 
//returns 81

//Function expression
const myFunc = function(a){
  const b = a*a ;
  console.log(b);
}
myFunc(9) 
//returns 81

//fucntion with Map
let arr = [1, 2, 3]
const sq = arr.map(function (v) { return v * v; });
console.log(sq) 
//returns arr as [ 1, 4, 9 ]
```
while using ES6, The `Arrow function` ensures more readable and clean code. When there is no function body, and only a single return value exits, Arrow function allows to omit the keyword `return` as well as the `{}` brackets surrounding the code.

ES6 version usage:
```javascript
//Immediately Invoked Function Expression (IIFE)
((a) => console.log(a*a))(6); //returns 36

//Function Expression with body
const myFunc = () => {
  const b = 89;
  return b;
}
console.log(myFunc()) 
//return 89

//Function Expression without body
const magic = () => new Date();
console.log(magic()); 
//returns the date

//Arrow functions with Map
var arr = [1, 2, 3];
arr = arr.map(n => n*n);
console.log(arr)      
// arr is [1, 4, 9]
```
### **Default Parameter**
---
The `Default Parameter` allows function parameters to have `default values`. It allows the programmer to define a parameter in advance. 

whenever the developer forgets to write the parameter, the function won’t return an undefined error because the parameter is already defined a default value using the `=` operator. So, when the function runs with a missing parameter, it will take the value of the default parameter, and will not return an error.

Default Parameter usage:
```javascript
//Here the function will increment the value by 1, if the increment value is not passed or passsed undefined.

const increment = (number, value = 1) => number + value;
console.log(increment(7));           
//returns 8
console.log(increment(7,undefined)); 
//returns 8
``` 
### **Rest Parameter**
---
The `Rest parameter (...)` allows a function to treat an indefinite number of arguments as an array i.e aggregation of remaining or extra arguments into single parameter collection.

Rest Parameter usage:
```javascript
//Here the x and y arguments accept the first and second parameter values and the extended ones are collected as an iterable collection a.

function f (x, y, ...a) { 
//Here a represents ["hello", true, 7] 
    return (x + y) * a.length;
}
console.log( f (1, 2, "hello", true, 7) === 9); 
//returns true
```
### **Spread Operator**
---
The `Spread operator` expands or spread the arrays and other expressions in places where multiple parameters or a collection of elements are expected. Its syntax is exactly the same as that of `Rest Operator`. 

However, the spread operator only works in-place, like in an argument to a function or in an array or Object literal.

This will not work:  `const spreaded = ...arr`  

Spread Operator usage:
```javascript
//ES5 concat() can be replaced with ES6 spread operator

var params = [ "hello", true, 7 ]
var other = [ 1, 2, ...params ] 
//other is [ 1, 2, "hello", true, 7 ]

//Spreading function parameters
function myFunc (x, y, z){
    return x + y + z;
}
console.log( myFunc(...[1,2,3]) == 6 );
//returns true

//Spreading string
var str = "foo"
var chars = [ ...str ] 
console.log(chars)
//rerturns an array [ "f", "o", "o" ]

//Spreading objects
var customer = { name: "RAj" }
var card = { amount: 7, product: "graphicsCard", price: 420 }
var k = {...card,...customer}
console.log(k)
//returns an object { amount: 7, product: 'graphicsCard', price: 420, name: 'RAj' }
```
### **Template Literal**
---
The `Template literal` also known as `Template strings` is a special type of string that helps constructing complex strings easier. Template literals can be used to create multi-line strings.

This new way of creating strings opens up flexible ways to create robust strings.  
To add variables to strings, drop the variable in a template string between the backticks (``) and wrap it with ${ and }. 

Template Literal usage:
```javascript
// Basic string creation using newline character in ES5

console.log("In JavaScript \n is a line-feed.")
/*returns
In JavaScript 
 is a line-feed.
*/

//Basic Template String creation without \n and + in ES6

var customer = { name: "RAj" };

var card = { amount: 7, product: "graphics Card", price: 420 };

var message = ` Hello ${customer.name},
Do you want to buy ${card.amount} ${card.product} for
a total of ${card.amount * card.price} bucks? `;

console.log(message);
/*returns
Hello RAj,
Do you want to buy 7 graphicsCard for
a total of 2940 bucks?
*/
```
### **Destructuring**
---
`Destructuring` provides cleaner ways to access values from array or an object and assign them to new variable easily.

ES5 syntax to destructure:
```javascript
var obj = {
  firstName:"Anil",
  lastName:"Kapoor",
  age:57
}
var firstName = obj.firstName
//Here firstName is "Anil"
var lastName = obj.lastName
//Here lastName is "kapoor"
var age = obj.age
//Here age is 57
```
With ES5, each value have to be assigned to each variable maually. whereas With ES6, values have to be put within curly brackets to get any property of the object.    
The name of the variable should be same as the name of the property of the object else it returns undefined, the variables can be renamed by using the colon `:` operator.  
If in some case the variable is not present in the object as key, by using `=` operator a default value can be set.

ES6 syntax to Destructure Objects:
```javascript
//Short-hand Object destructuring
const obj = {
  firstName: "Anil",
  lastName: "Kapoor",
  age: 57,
}
const { firstName, lastName, age } = obj;
//Here firstName = "Anil" lastName = "kapoor" and age = 57

//New variable name and dealing with undefined values 
const obj = {
  firstName: "Anil", lastName: "Kapoor", age:57
}
const { firstName : first, lastName, phone = 255895, age } = obj;
//Here first = "Anil" lastName = "kapoor" phone = 255895 and age = 57

//Destroying object function parameters
function g ({ name: n, val}) {
    val = 65
    console.log(n, val)
}
g({ name: "Anil", val: 57})
//returns 'Anil' 65

//Destroying nested objects
const obj = {
  name: "Anil Kapoor",
  address: {
    city: "Bangalore",
    postal: 560059
  }
}
const{ address: {city: place, postal}} = obj

```
ES6 syntax to Destructure Arrays:
```javascript
//Destroying Arrays
var list = [ 1, 2, 3 ]
var [ a, , b ] = list
//Here a = 1 and b = 3

//Short hand for swapping variable
[ b, a ] = [ a, b ]
/* Earlier a = 1 and b = 3
now a = 3 and b = 1
*/

//Dealing with undefined values 
var list = [ 7, 42 ]
var [ a, b = 2, c = 3, d ] = list
//Here a = 7, b = 42, c = 3, d = undefined

//Destroying function Parameters
function f ([ name, age]) {
  name = "Raju"
    console.log(name, age)
}
f([ "Amit", 42 ])
//returns "Raju" 42
```
### **Modules**
---
`Modules` provide a new way to share code easily among different JavaScript files. It makes JavaScript code more modular, clean, and maintainable.  
Modules can be used by using `import` and `export`. Export involves exporting modules of a file for use in one or more other files, whereas import is used to grab the modules from a file in need.

Exporting multiple named modules:

```javascript
//  rj/math.js
const prod = (x, y) => {
  return x * y;
}
const add = (a, b) => {
  return a + b;
}

export { add, prod };
//exporting add and prod function together
export var pi = 3.14;
//exporting a single variable
```

Importing only the prod funtion and pi variable:
```javascript
// otherApp.js

import { prod, pi } from "rj/math.js";

console.log(" π*π = " + prod(pi, pi));
//returns π*π = 9.8596
```
Importing everything from file `rj/math.js` and saving it in a variable `math`:
```javascript
//  someApp.js

import * as math from "rj/math.js";

console.log(" π*π = " + math.sum(math.pi, math.pi));
//returns π*π = 9.8596
```
Export `default` is used when only one value or a function is being exported from a file.  
Export default file:
```javascript
//rj.math

export default function sum (x, y) { return x + y };
//exporting the inline function
```
During export default any variable name can be used at the import file except `{}` or `*`.  
Importing from default exporting file:
```javascript
//app.js 

import add from "rj/math.js";

add(3 + 4)
//return 7
```
### **Class**
---
A `Class` is a type of function, but instead of using the keyword function, the keyword class is used to initiate it.  

In a class the name always starts with capital letter and the properties are assigned inside a `constructor()` method.  
The constructor() method is compulsary to use with class. The constructor method is called each time the class object is initialized.  

Classes in ES5 was implemented by using the `this` keyword and new properties were added/extended by using `prototype` keyword. 

ES5 class implementation using function expression: 
```javascript
//ES5 Class
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.getName = function() {
  return this.name;
};

var person1 = new Person("arun",67);
console.log(person1.getName());
//returns person1 name as arun
```
ES6 Class supports *prototype-based inheritance*, *super calls*, *instance and static methods* as well as *constructors*.  

ES6 class implementation using Class keyword and constructor method:
```javascript
//ES6 Class 
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
getName() {
    return this.name;
  }
}
var person1 = new Person("arun",67);

console.log(person1.getName());
//rerturns person1 name as arun

//inheritance
class Teacher extends Person {
  constructor(name, age, subject) {
    super(name, age);

    this.subject = subject;
  }
  about(){
    return `${this.name} ${this.age} ${this.subject}`
  }
}
var teacher1 = new Teacher("arun",67,"maths");

console.log(teacher1.about());
//returns arun 67 maths
```
### **Promise**
---
A `promise` is an object that may produce a single value some time in the future: either a resolved value, or an error or reason that it is not resolved asynchronously.  

Promise is a constructor function so, `new` keyword is used to create one. It takes a function, as its argument, with two parameters - `resolve` and `reject`.

A Promise has three states:
1. pending: initial state, neither fulfilled nor rejected.
2. fulfilled: meaning that the operation was completed successfully.
3. rejected: meaning that the operation failed.

Before Promises, async calls were handled by Callbacks. Promises resolved the Call Back Hell.  

Promise usage:
```javascript
let p = new Promise( (resolve, reject) => {
  let sum = 2 + 3
  if(sum == 5){
    resolve("success")
  }else{
    reject({ 
      name:"Failed",
      mes:"sum is not equal to 5"
      })
  }
} );

p.then(
  (message) =>{
    console.log(message+" from resolved then ")
  }
).catch((error) => {
  console.log(error.name+" from catch as"+ error.mes)
})
//Here the promise gets resolved and returns "success from resolved then "

//if sum = 6 then the promise gets rejected and returns "Failed from catch as sum is not equal to 5" 
```
### **Symbol**
---
A `Symbol` is a primitive datatype just like Number, String, or Boolean. They are unique and immutable, but not private since they are exposed via reflection features like `Object.getOwnPropertySymbols()`.

Symbol can have an optional `description`, but for debugging purposes only.


Symbol usage:
```javascript
Symbol("foo") === Symbol("foo")      // false
Symbol.for("cat")==Symbol.for("cat") // true

const foo = Symbol();
const bar = Symbol();

typeof foo === "symbol" //true
typeof bar === "symbol" //true

let obj = {}
obj[foo] = "foo"
obj[bar] = "bar"
console.log(obj)    // returns { Symbol(): "foo", Symbol(): "bar" }
JSON.stringify(obj) // {}
Object.keys(obj)    // []
Object.getOwnPropertyNames(obj)   // []
Object.getOwnPropertySymbols(obj) // [ foo, bar ]
```
### **Set Datastructures**
---
The `Set` object is used to store unique values of any type. Set objects are collections of values which can be iterated in insertion order.

 A value in the Set may only occur once and it is unique in the Set's collection.

Set usage:
```javascript
//Creating a set s using new keyword 
let s = new Set()

//adding values to the set s
s.add("hello").add("goodbye").add("hello")
//Here s is Set { 'hello', 'goodbye' }

//comparing the size of set s with 2
s.size === 2            //true

//checking if the set contains the string hello 
s.has("hello") === true //true

//Iterating through set s values in insertion order and printing the values
for (let key of s){
    console.log(key);
}
/* prints
hello
goodbye
*/
```
### **For/Of Loop**
---
The `for/of` statement is used to loop through the values of data structures that are iterable such as Arrays, Strings, Maps, NodeLists etc.

The for/of loop has the following syntax:
```javascript
for (variable of iterable) {
  // code block to be executed
}
```
* variable - For every iteration the value of the next property is assigned to the variable. Variables can be declared with const, let, or var.

* iterable - An object that has iterable properties.
```javascript
//Array
var arr=["one","two","three"]
for(var element of arr){
  console.log(element)
}
/*prints
"one"
"two"
"three"
*/

//Strings
var str="for"
for(var character of str){
  console.log(character)
}
/*prints
f
o
r
*/

//Set
const iterable = new Set([1, 1, 2, 2, 3, 3]);

for (const value of iterable) {
  console.log(value);
}
/*prints
1
2
3*/
```
### **Exponentiation Operator**
---
The `Exponentiation operator` (`**`) raises the first operand to the power of the second operand. It produces the same result as `Math.pow()`

Exponentiation Operator usage:
```javascript
//ES5 Math.pow()
var x = 2, y = 6;
var p = Math.pow(6,2); //p is 36

//ES6 Exponentiation Operator 
var a = 6;
var b = a**2;  //b is 36
```

### **New Built-in Methods**   
---
* ### **Arrays**

  * ### Array.find()
    The `find()` method returns the first array element that passes the test function.   
    The find() method takes 3 arguments:
    1. The item value
    2. The item index
    3. The array itself

    Array.find() usage:
    ```javascript
    var array = [1,2,3,4];

    var firsteEven = array.find((value, index, array) => value%2 == 0) //even is elemnt 2 of array 
    ```

  * ### Array.findIndex()
    The `findIndex()` method returns the index of the first array element that passes the test function.  

    The findIndex() method takes 3 arguments:
    1. The item value
    2. The item index
    3. The array itself

    findIndex() usage:
    ```javascript
    var array = [4, 9, 16, 25, 29];

    var firstGreater = array.findIndex((value, index, array) => value > 18);
    // firstGreater is index value 3 of array
    ```
  * ### Array.from()
    The `from()` method creates a new array, from an array-like or iterable object.

    from() usage:
    ```javascript
    //Sets
    Array.from(new Set("zoom")));
    //returns Array ["z", "o", "m"]
    
    //strings
    Array.from('foo'));
    //returns Array ["f", "o", "o"]  
    
    //Arrays
    Array.from([1, 2, 3], x => x + x));
    //returns Array [2, 4, 6]
    ``` 

  * ### Array.fill()
    The `fill()` method is used to fill an array with a particular value and in a range of index as well.
    
    The fill() method takes 3 arguments:
    1. The value to fill 
    2. The start index
    3. The end index
    
    fill() method usage:
    ```javascript
    //Fills an array with the given value:
    
    ['a', 'b', 'c'].fill(7)
    //returns [ 7, 7, 7 ]

    //Holes [1:2] get no special treatment:
    
    var arr = new Array(3).fill(7)
    // arr is [ 7, 7, 7 ]
    
    //Restrict where the filling starts and ends:

    ['a', 'b', 'c'].fill(7, 1, 2)
    // returns [ 'a', 7, 'c' ]
    ```
* ### **Strings**
    * ### String.startsWith()
      The `startsWith()` method determines whether a string begins with the characters of the specified string, returning true if starts with it or false if not.

      The startsWith() method takes two parameter:
      1. search String 
      2. position

       ```javascript 
       //checks from index 0
       "hello".startsWith('hel')     // returns true 
       
       //checks from index 1
       "hello".startsWith("ello", 1) // returns true
       ```

    * ### String.endsWith()
      The `endsWith()` method determines whether a string end with the characters of the specified string, returning true if ends with it or false if not.

      The endsWith() method takes two parameter:
      1. search String 
      2. length

       ```javascript 
       //checks from index 0
       "hello".startsWith('lo')     // returns true 
       
       //checks from index 1
       "hello".startsWith("ell", 5) // returns true
       ```
    * ### String.includes()
      The `include()` method is used to determine whether the specified string contains the sub-string or not. It returns true if the sub-string exists otherwise, returns false.

      ```javascript
      "hello".includes("ell")       // true
      "hello".includes("ell", 1)    // true
      "hello".includes("ell", 2)    // false
      ```
    * ### String.repeat()
      The `repeat()` method is used to create a new string with same strings repeated linearly , it accepts a number that represents repetition number of that string.

      Repeat() usage:    
        ```javascript
        "foo".repeat(3) // returns "foofoofoo"
        ```  
* ### **Objects**
  * ### Object.assign()
    The `assign()` method is used to copy all enumerable own properties from one or more source objects to a target object. It returns the target object.
    
    assign() method accepts two parameters:
    1. target = The target object where the source properties are applied.
    2. sources = The source object contains the properties to be applied on target. 

    ```javascript
    const target = { a: 1, b: 2 };
    const source = { b: 4, c: 5 };

    const returnedTarget = Object.assign(target, source);

    console.log(target);
    // returns Object { a: 1, b: 4, c: 5 }

    console.log(returnedTarget);
    // returns Object { a: 1, b: 4, c: 5 }

---

## **Conclusion** 
This paper covers about ES6 and some its main features. Through this paper a number of improvements can be judged with respect to the previous verion of ECMAScript.

## **Sources**

* [MDN Web Docs](https://developer.mozilla.org/en-US/)

* [W3 School](https://www.w3schools.com/)

* [freeCodeCamp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)
* [ECMAScript® 2015 Language Specification](https://262.ecma-international.org/6.0/)
