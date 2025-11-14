# Javascript_notes
#Q1. What is JavaScript?

JavaScript is a high-level, interpreted scripting language used to make web pages interactive and dynamic. It runs in the browser (client-side) and can also run on the server (Node.js).

Key Points:

Enables dynamic behavior in web pages.

Works with HTML (structure) and CSS (style).

Single-threaded and interpreted language.

Supports event-driven, functional, and object-oriented programming.

#Q2. History of JavaScript?

Created by: Brendan Eich in 1995 at Netscape.

Purpose: To make web pages interactive and dynamic (browsers only had HTML & CSS then).

Initial name: Mocha → LiveScript → JavaScript (final name chosen for marketing reasons).

Standardization:

In 1997, JavaScript was standardized by ECMA International as ECMAScript (ES).

Major Versions:

ES1 (1997): First edition.

ES5 (2009): Added strict mode, JSON support.

ES6 (2015): Big update — let, const, classes, arrow functions, modules, etc.

Later versions: ES7, ES8, … add modern features each year.

#Q3. How to Run JavaScript?

You can run JavaScript in two main environments:

1. In a Web Browser (Client-side)
Every browser (Chrome, Firefox, Edge, etc.) has a built-in JS engine.

You can run JS: inside html file
<script>
  console.log("Hello JavaScript");
</script>
Or link an external file: 
<script src="script.js"></script>
2. In Node.js (Server-side)

Install Node.js → https://nodejs.org

Save code in app.js file, then run:
node app.js
Output appears in terminal.


#Q4. Difference between var, let, and const
Feature               	var	                                                   let	                                                              const
scope                 	Function-scoped                                   	Block-scoped          	                                           Block-scoped
Re-declaration	        ✅ Allowed	                                     ❌ Not allowed           	                                          ❌ Not allowed
Re-assignment	          ✅ Allowed                                     	✅ Allowed	                                                        ❌ Not allowed
Hoisting	              ✅ Hoisted (initialized as undefined)	            ✅ Hoisted (not initialized → Temporal Dead Zone)	          ✅ Hoisted (not initialized → Temporal Dead Zone)
Use Case	              Older JS code                                   	When value changes                                               	When value is fixed

#Q5. What is Hoisting?
Hoisting is javascript's default behaviour of moving declaritions to the top.
Declarition can be both variable and function
Actual code:-  console.log(a);
               var a = 5;
How jaavascript interperter see:- //hoisting
                                  var a;
                                  console.log(a);
                                  var a = 5;

                                  
#Q6. Variable Naming Rules?
  Must start with
→ a letter (a–z or A–Z), underscore (_), or dollar sign ($)
let name, _count, $price; // ✅ valid
let 1item; // ❌ invalid
  Can contain letters, numbers, underscores, and dollar signs
let user1, user_name, $data; // ✅ valid
  Cannot use JavaScript reserved keywords
  ❌ Invalid:
let for = 10;
var class = 'A';
const return = 5;

#Q7. Variable Scope?
Scope means where a variable is accessible in your code — or in simple words,
➡️ “the area where a variable can be used or recognized.”

1. Global Scope

A variable declared outside any function or block.

Accessible everywhere in the program.
let name = "Mohit"; // global scope

function greet() {
  console.log(name); // ✅ accessible here
}
console.log(name);   // ✅ accessible here too
2. Function Scope (Local Scope)

Variables declared inside a function using var, let, or const
are only accessible within that function.
function showAge() {
  let age = 21; // local to function
  console.log(age); // ✅ works
}
showAge();
// console.log(age); ❌ Error: age is not defined
3. Block Scope

Introduced with let and const (not with var).

Variables declared inside { ... } (curly braces)
are accessible only within that block.
{
  let x = 10;
  const y = 20;
  console.log(x, y); // ✅ works
}
// console.log(x, y); ❌ Error (block scope)
var is not block-scoped, it ignores {}:
{
  var z = 30;
}
console.log(z); // ✅ works (function or global scope)
4. Lexical (Nested) Scope

Inner functions can access variables from their outer function,
but not vice-versa.
function outer() {
  let a = 10;
  function inner() {
    console.log(a); // ✅ inner can access outer variable
  }
  inner();
}
outer();
5. Global Object Scope (Browser Only)

Variables declared with var in the global scope
become properties of the global object (window in browser).
var city = "Delhi";
console.log(window.city); // ✅ works

let state = "UP";
console.log(window.state); // ❌ undefined

#Q8. Define Block Scope, Function Scope, Global Scope

               Block Scope
               
A block means anything inside { } (curly braces).
Variables declared with let or const are block-scoped,

meaning they exist only inside that block.
{
  let a = 10;
  const b = 20;
  console.log(a, b); // ✅ Accessible inside the block
}
console.log(a, b);   // ❌ Error: not defined outside

var is not block-scoped — it ignores {}.
{
  var x = 30;
}
console.log(x); // ✅ Works (var has function/global scope)

           Function Scope

Variables declared inside a function are only accessible inside that function.
They are not visible outside.

function greet() {
  let message = "Hello!";
  console.log(message); // ✅ Accessible here
}
greet();

console.log(message); // ❌ Error: message is not defined
var, let, and const all follow function scope (but let and const are also block-scoped inside the function).

            Global Scope

A variable declared outside any function or block
is called a global variable — it can be accessed anywhere in the code.

let name = "Mohit"; // global variable

function showName() {
  console.log(name); // ✅ Accessible here
}

console.log(name); // ✅ Accessible here too
showName();

            

           



                                  
