# typeScript Interview Questions

## typeScript Basic Interview Questions

<details>
<summary>
1.<b> What is TypeScript?</b>
</summary>

`TypeScript` is an open-source object-oriented programming language developed and maintained by Microsoft. It is a superset of JavaScript.

`TypeScript` is designed for the development of large applications and transpiles to JavaScript.
</details>


<details>
<summary>
2.<b> Why do we need TypeScript?</b>
</summary>

`TypeScript` is an attempt to fix JavaScript problems.

Since we all know that JavaScript is the only language used in client-side scripting as browsers can only understand JavaScript.

Since TypeScript simplifies JavaScript code, making it easier to read and debug. It saves developers time and increases productivity.
</details>


<details>
<summary>
3.<b> How to install TypeScript?</b>
</summary>

There are two ways to install typescript:

Using npm (Node Package Manager) Install the TypeScript plugin in your IDE

```jsx harmony 
npm install -g typescript

```
You can also install a typescript plugin available for your IDE. You can use IDE of your choices such as VS Code, Visual Studio, Atom, or Sublime Text.
</details>


<details>
<summary>
4.<b> What is TypeScript and how does it differ from JavaScript?</b>
</summary>

**TypeScript** is a statically-typed superset of JavaScript, developed and maintained by Microsoft. It enables enhanced code maintainability and predictability. After compiling, TypeScript code is transpiled into standard, browser-compatible JavaScript.

Key distinctions between TypeScript and JavaScript include the use of type annotations, the ability to work with existing JavaScript code, and more.

**TypeScript Features & Benefits**

**Type System**: Offers static typing, allowing developers to define the type of variables, parameters, and return values. This helps catch errors during development, reducing runtime issues.

**Advanced Language Features**: Incorporates modern ECMAScript syntax and features, often before they are rolled out in JavaScript. Additionally, TypeScript brings functional programming patterns, classes, and access modifiers (such as public and private)

**Compatibility with JavaScript**: TypeScript can interpret existing JavaScript code with minor or no modifications.

**Tooling and Extra Safety**: Provides enhanced autocompletion, refactoring, and documentation via TypeScript-aware tools. TypeScript helps catch and rectify common programming errors without needing to run the code.

**ECMAScript Compatibility**: TypeScript allows developers to target different ECMAScript versions, ensuring the generated JavaScript is compatible with the targeted browsers.

**Code Structure & Readability**: Promotes maintainability by enforcing a defined coding structure and fostering code clarity.

**TypeScript's Role in Modern Development**

**Workplace Adaptability**: TypeScript is used in an extensive range of projects, from small utilities to large-scale applications.

**Community Support**: Supported by a vibrant developer community, TypeScript benefits from frequent updates, bug fixes, and useful extensions.

**On-Going Development**: A robust language server furnishes accurate tooling feedback, such as linting and error suggestions in real time.

**Rapid Enhancement**: The TypeScript team consistently introduces new features and reinforces existing ones.


</details>

<details>
<summary>
5.<b> Can you explain what is meant by "TypeScript is a superset of JavaScript"?</b>
</summary>

`TypeScript` is often described as a **"superset of JavaScript"** because every valid JavaScript code is also a valid TypeScript code.

TypeScript is designed in a way that it fully embraces existing `JavaScript syntax` and functionality. This ensures a smooth transition for developers wishing to adopt or migrate to TypeScript.

**Key TypeScript Features On Top of JavaScript**

**Type Definitions**: TypeScript introduces static typing through type annotations. These are optional, enabling gradual adoption for existing codebases that might not need them.

**Newer JavaScript Features**: TypeScript extends JavaScript syntax, providing support for the latest ECMAScript standards more effectively through its compiler, even when the underlying JavaScript engine might not support them yet.

**Tooling and Error Detection**: TypeScript offers robust type-checking, increased code readability, and stronger compile-time error detection.

**Code Demonstration**
Here is the TypeScript code:


```jsx harmony 
let num: number = 5;
num = "this will raise a type error";

```
</details>


<details>
<summary>
6.<b> Explain the TypeScript program execution? </b>
</summary>

TypeScript totally follows the `OOPS` (Object-Oriented Programming System) concept and with the help of TSC (TypeScript Compiler), we can convert Typescript code (.ts file) to JavaScript (.js file).
</details>


<details>
<summary>
7.<b> What OOPs does TypeScript support?</b>
</summary>

Typescript supports the four pillars of any object-oriented programming language that are – `Abstraction`, `Polymorphism`, `Inheritance`, and `Encapsulation`.
</details>


<details>
<summary>
8.<b>  Explain data types in TypeScript?</b>
</summary>

`Typescript` supports Any, Built-in, and User-defined data types.

Any is the superset for all the data types available. It means that the variable could be of any type. It will override the type checking.

The Built-in types include `string`, `number`, `boolean`, `undefined`, `null`, and `void`.

The User-defined types include `array`, `enum`, `interface`, `class`, `union`, and `tuple`.
</details>


<details>
<summary>
9.<b> What are the modules in TypeScript?</b>
</summary>

A `module` is a way to construct a local scope in a file. So that all the classes, variables declared in a module are not accessible outside the module.

We can create a module using the export keyword. A module in typescript can be used in another module using the import keyword.
</details>


<details>
<summary>
10.<b> What is a namespace in TypeScript?</b>
</summary>

Using namespace we can group logically related code. This is built into typescript, unlike javascript. A namespace can include classes, interfaces, functions, and variables.

We can create a namespace in typescript using namespace keyword followed by any valid name.

For Example:

```jsx harmony 

namespace MyNamespace {

}
```
</details>


<details>
<summary>
11.<b> What are typed functions in TypeScript?</b>
</summary>

In Typescript, a function can be created as a named function or anonymous function. We can further add types to each of the parameters and to the function as well.

```jsx harmony 


// Named function
function add(a: number, b: number) : number {
    return a + b;
}

// Anonymous function
let funcAdd = function(a: number, b: number): number { return a + b; };
```

If we want to write the full type of the function:

```jsx harmony 

let funcAdd: (a: number, b: number) => number = 
     function (a: number, b: number) : number  { return a + b; };
```
</details>

<details>
<summary>
12.<b> What is as syntax in TypeScript?</b>
</summary>
This is an additional Type assertion syntax. The reason for including the as syntax in typescript was that conflicted with JSX.

```jsx harmony 

let strLength: number= (someString as string).length;
```

</details>

<details>
<summary>
13.<b> Difference between readonly and const?</b>
</summary>

The difference between readonly and const is: const is used on a variable whereas read-only is used on properties of an object.
</details>


<details>
<summary>
14.<b> What are static properties?</b>
</summary>

Static properties are those that are shared by all the instances of a class and they can be accessed via the class name and dot operator.


```jsx harmony 

class Singleton {
    static counter = 0;
    constructor() {
        Singleton.counter++;
    }
  }
  
  var singleton = new Singleton();
  console.log(Singleton.counter); //1
```
</details>


<details>
<summary>
15.<b>  Explain access modifiers in Typescript?</b>
</summary>

There are 3 types of access modifiers in TypeScript: `public`, `private`, and `protected`.

**Public**
By default, all the members of a class are public in TypeScript.

**Private**
When any of the class members are declared private, it is only accessible within the class scope.

**Protected**
The protected members are similar to private access modifiers, except that they are accessible in the derived class.
</details>

<details>
<summary>
16.<b> Can you explain Rest parameters in Typescript?</b>
</summary>

Sometimes, we want to work with multiple parameters as a group, or we may not know how many parameters a function will ultimately take. In JavaScript, we have something known as arguments. Similarly, we have Rest parameters in typescript.

Rest parameters are treated as a boundless number of optional parameters. The compiler will build an array of the arguments passed in with the name given after the ellipsis (…)

```jsx harmony 

function getPlayersList(name:string, ...players: string[]) {
    return name + " " + players.join(" ");
}

let players = getPlayersList("Virat", "MS", "Warner", "Kane", "Ben")
```
</details>


<details>
<summary>
17.<b> What are Generics in TypeScript?</b>
</summary>

Generics in `Typescript` is no different than generics in other programming languages like `C#` or  `Java`.

You can create a class, an interface, or a function that works with different types, without specifying the type upfront.

```jsx harmony

function greet(a : T) {
  console.log(`Hi ${a}!`)
}

greet('DS'); //function call

```

The symbol `T` identifies a generic type.
</details>


<details>
<summary>
18.<b> What is Modules in TypeScript?</b>
</summary>

A module is a way to construct a local scope in a file. So that all the classes, variables declared in a module are not accessible outside the module.

👉 We can create a module using the export keyword. 👉 A module in typescript can be used in another module using the import keyword.

```jsx harmony 

export class Student {
    readonly Id: number;
    Name: string;
    
    constructor(id: number, name: string) {
        this.Id = id;
        this.Name = name;
    }
}

let Subject: string = "Computer Science";
```
</details>


<details>
<summary>
19.<b> Can we use JSX in TypeScript?</b>
</summary>

Yes, JSX is an embeddable XML-like syntax.

In order to use JSX, we must name our file with a .tsx extension and should enable jsx option.

</details>


<details>
<summary>
20.<b> What are Decorators in TypeScript?</b>
</summary>

`Decorators` are functions that modify a class, property, method, or method parameter. The syntax to define decorators is “@”.

In other words, `Decorators` are functions that take their target as the argument.
</details>


<details>
<summary>
21.<b> What is Triple-Slash Directive?</b>
</summary>

Triple-slash directives are single-line comments containing a single XML tag. The contents of the comments are used as compiler directives.

```jsx harmony 

 /// <reference path = "filename.ts" />
```

Triple-slash directives are only valid at the top of their containing file.
</details>


<details>
<summary>
22.<b> What is the ts.config file in Typescript?</b>
</summary>

The `typescript` project will have a ts.config file which provides an infinite number of ways to customize the behavior of the compiler. typescript interview questions

</details>



<details>
<summary>
23.<b> Is it possible to compile a typescript file automatically?</b>
</summary>

Yes, it is possible using --watch option while compiling the typescript file for the first time.

```jsx harmony 

tsc --watch filename.ts
```
</details>


<details>
<summary>
24.<b> Explain the Declare keyword in Typescript?</b>
</summary>

The declare keyword is used for ambient declarations and methods where you want to define a variable that may exist elsewhere.

If we want to use any library in our TypeScript code, we can use the following code:

```jsx harmony 

declare var myAlexaLibrary;
```
</details>


<details>
<summary>
25.<b> Explain the need for a TypeScript Definition Manager?</b>
</summary>

TypeScript Definition Manager (TSD) is a package manager used to search and install typescript definition files directly from the community-driven DefinitelyTyped repository.

Now, if you want to use some jQuery code in your .ts file:

```jsx harmony 


$(document).ready(function() { //Your jQuery code });
```
Here, when you try to compile it by using tsc, it will give a compile-time error: Cannot find the name “$”.

So, you need to inform the TypeScript compiler that “$” is belongs to jQuery.

To do this, TSD comes into play. You can download the jQuery Type Definition file and include it in our .ts file.
</details>


<details>
<summary>
26.<b> How to debug a TypeScript file?</b>
</summary>

To debug any TypeScript file, we need a .js source map file. So, we have to compile the .ts file with the --sourcemap flag to generate a source map file.

```jsx harmony 

$ tsc -sourcemap filename.ts
```

This will create a filename.js and filename.js.map. And the last line of filename.js would be a reference to the source map file.

```jsx harmony 

//# sourceMappingURL=filename.js.map
```
</details>


<details>
<summary>
27.<b>What are the difference beetween Typescript and JavaScript? </b>
</summary>

- It is an object oriented programming language (not pure).
- Here it is static typing (We can declare a variable in multiple ways). ex: var num : number.
- It has interfaces.
- It has optional parameter feature.
- It has Rest Parameter feature.
- Supports generics.
- Supports Modules
-  Number, string etc. are the interfaces.

</details>


<details>
<summary>
28.<b> How to call base class constructor from child class in TypeScript? </b>
</summary>

We can call base class constructor using `super()`.
</details>


<details>
<summary>
29.<b> What is Interface in TypeScript? </b>
</summary>

One of TypeScript’s core principles is that type-checking focuses on the shape that values have.

An `interface` is a virtual structure that only exists within the context of TypeScript. The TypeScript compiler uses interfaces solely for type-checking purposes.

When you define your interface you’re saying that any object (not an instance of a class) given this contract must be an object containing interfaces properties.
</details>


<details>
<summary>
30.<b> When to use interfaces and when to use classes in TypeScript?</b>
</summary>

If you need/wish to create an instance of perhaps a custom object, whilst getting the benefits of type-checking things such as arguments, return types or generics - a class makes sense.

**If you’re not creating instances** - we have interfaces at our disposal, and their benefit comes from not generating any source code, yet allowing us to somewhat “virtually” type-check our code.
</details>


<details>
<summary>
31.<b> What is the difference between Classes and Interfaces in Typescript?</b>
</summary>

We use classes as object factories. A class defines a blueprint of what an object should look like and act like and then implements that blueprint by initialising class properties and defining methods. Classes are present throughout all the phases of our code.

Unlike classes, an interface is a virtual structure that only exists within the context of TypeScript. The TypeScript compiler uses interfaces solely for type-checking purposes. Once code is transpiled to its target language, it will be stripped from interfaces.

A class may define a factory or a singleton by providing initialisation to its properties and implementation to its methods, an interface is simply a structural contract that defines what the properties of an object should have as a name and as a type.
</details>


<details>
<summary>
32.<b> What is "Decorators" in TypeScript? </b>
</summary>

A **Decorator** is a special kind of declaration that can be attached to a class declaration, method, accessor, property, or parameter. Decorators are functions that take their target as the argument. With decorators we can run arbitrary code around the target execution or even entirely replace the target with a new definition.

There are 4 things we can decorate in `ECMAScript2016` (and Typescript): constructors, methods, properties and parameters.
</details>


<details>
<summary>
33.<b> What is getters/setters in TypeScript?</b>
</summary>

TypeScript supports `getters/setters` as a way of intercepting accesses to a member of an object. This gives you a way of having finer-grained control over how a member is accessed on each object.

```jsx harmony 
class foo {
  private _bar:boolean = false;

  get bar():boolean {
    return this._bar;
  }
  set bar(theBar:boolean) {
    this._bar = theBar;
  }
}

var myBar = myFoo.bar;  // correct (get)
myFoo.bar = true;  // correct (set)
```
</details>



<details>
<summary>
34.<b> How could you check null and undefined in TypeScript? </b>
</summary>

Just use:

```jsx harmony 
if (value) {
}
```

It will evaluate to `true` if `value` is not:

`null`
`undefined`
`NaN`
empty string `''`
`0`
`false`
TypesScript includes JavaScript rules.
</details>


<details>
<summary>
35.<b> How to implement class constants in TypeScript?</b>
</summary>

In TypeScript, the const keyword cannot be used to declare class properties. Doing so causes the compiler to an error with "A class member cannot have the 'const' keyword." TypeScript 2.0 has the readonly modifier:

```jsx harmony 

class MyClass {
    readonly myReadonlyProperty = 1;

    myMethod() {
        console.log(this.myReadonlyProperty);
    }
}

new MyClass().myReadonlyProperty = 5; // error, readonly
```
</details>

<details>
<summary>
36.<b> Could we use TypeScript on backend and how?  </b>
</summary>

Typescript doesn’t only work for browser or frontend code, you can also choose to write your backend applications. For example you could choose Node.js and have some additional type safety and the other abstraction that the language brings.

1. Install the default Typescript compiler

```jsx harmony 
npm i -g typescript
```

2. The TypeScript compiler takes options in the shape of a tsconfig.json file that determines where to put built files and in general is pretty similar to a babel or webpack config.

```jsx harmony 
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "declaration": true,
    "outDir": "build"
  }
}

```

3. Compile ts files

```jsx harmony 
tsc
```

4. Run

```jsx harmony 

node build/index.js
```
</details>


<details>
<summary>
37.<b> Which object oriented terms are supported by TypeScript? </b>
</summary>

TypeScript supports following object oriented terms:

- Modules
- Classes
- Interfaces
- Data Types
- Member functions
</details>



<details>
<summary>
38.<b> What is a TypeScript Map file?</b>
</summary>

`.map` files are source map files that let tools map between the emitted JavaScript code and the TypeScript source files that created it. Many debuggers (e.g. Visual Studio or Chrome's dev tools) can consume these files so you can debug the TypeScript file instead of the JavaScript file.

</details>


<details>
<summary>
39.<b> Are strongly-typed functions as parameters possible in TypeScript?</b>
</summary>

Consider the code:

```jsx harmony 
class Foo {
    save(callback: Function) : void {
        //Do the save
        var result : number = 42; //We get a number from the save operation
        //Can I at compile-time ensure the callback accepts a single parameter of type number somehow?
        callback(result);
    }
}

var foo = new Foo();
var callback = (result: string) : void => {
    alert(result);
}
foo.save(callback);
```

Can you make the result parameter in save a type-safe function? Rewrite the code to demonstrate.

</details>


<details>
<summary>
40.<b> Is that TypeScript code valid? Explain why.</b>
</summary>

Consider:

```jsx harmony 
class Point {
    x: number;
    y: number;
}

interface Point3d extends Point {
    z: number;
}

let point3d: Point3d = {x: 1, y: 2, z: 3};
```
</details>


<details>
<summary>
41.<b> What are the basic types available in TypeScript?</b>
</summary>

**TypeScript** provides an assortment of basic types for different kinds of data, such as numbers, strings, boolean values, arrays, tuples and more.

**Common Basic Types in TypeScript**

**Boolean**: Represents true/false values.

**Number**: Applies to both integer and floating-point numbers.

**String**: Refers to textual data.

**Array**: Offers a flexible way to work with structured data.

**Tuple**: Enables the definition of arrays with a fixed number of elements, each potentially of a different data type.

**Enum**: Provides a set of named constants such as days or colors.

**Any**: Offers a dynamic type, which can be used to bypass type-checking. It's typically best to be avoided, as it defeats the purpose of using TypeScript, which is primarily focused on static typing. However, there are certain use cases where it becomes necessary.

**Void**: Typically used as the return type for functions that don't return a value.

**Null and Undefined**: Allow for the assignment of null and undefined values, respectively. However, this isn’t enabled by default, and these are probably better handled using the strict mode settings in TypeScript.

**Never**: Represents the type of values that never occur. For instance, the return type of a function that doesn't reach its end or always throws an error.

**Object**: Any JavaScript object.

**Function**: Denotes a function type.

**Code Example**: **Basic TypeScript Types**
Here is the TypeScript code:

```jsx harmony 
// Boolean
let isActive: boolean = true;

// Number
let age: number = 30;

// String
let title: string = "Manager";

// Array
let scores: number[] = [85, 90, 78];
// or use a compact form: let scores: Array<number> = [85, 90, 78];

// Tuple
let employee: [string, number, boolean] = ['John', 35, true];

// Enum
enum WeekDays { Monday, Tuesday, Wednesday, Thursday, Friday }
let today: WeekDays = WeekDays.Wednesday;

// Any
let dynamicData: any = 20;

// Void
function greet(): void {
  console.log("Hello!");
}

// Null and Undefined
let data: null = null;
let user: undefined = undefined;

// Never
function errorMessage(message: string): never {
  throw new Error(message);
}

// Object
let person: object = {
  name: 'John',
  age: 30
};

// Function
let calculate: Function;
calculate = function (x: number, y: number): number {
  return x + y;
};
```
</details>


<details>
<summary>
42.<b> How do you declare variables in TypeScript?</b>
</summary>

In TypeScript, `variable declarations` support different methodologies for declaring variables and their associated types.

**Variable and Type Declaration Methods**

1. **var**

```jsx harmony 
var score: number = 100;
```

This declaration can lead to **variable hoisting** and has global scope or function-level scope.

2. **let**
Use let when you want to define variables within a **block scope**. This is the recommended default choice:

```jsx harmony 
let playerName: string = "John";
```

3. **const**
const allows you to declare **constants** and is especially useful for maintaining data integrity:

```jsx harmony 

const apiKey: string = "your-api-key-here";
```

4. **Function Scope**
All three methods (`var`, `let`, and `const`) are confined to their immediate function scope

```jsx harmony 
function doSomething() {
  let tempValue: number = 42;
  var result: boolean = true;
}
```

**Rules for Variable Declaration and Initialization**

**Order Matters**: In TypeScript, a variable must be declared before being used. This is not a requirement in JavaScript, but good JavaScript practice is to declare a variable before using it.

If you're dealing with complex or interconnected codes, it's a good practice to use the let and const declarations that ensure the block-level scoping, thus helping with potential hoisting issues.

**Static Types**: TypeScript requires that you declare the data type of a variable (or let the system infer it) and then initialize it with a value of exactly the same type:

```jsx harmony 
let count: number;  // Declaration
count = 42;  // Allowed
count = "42";  // Error! Type 'string' is not assignable to type 'number'.
```

Type Inference: TypeScript can often infer the variable's type based on its initialization value. This reduces the need to specify a type explicitly.

```jsx harmony 
let word = "hello!";  // TypeScript infers the type as 'string' because of the initialization.

```

**Best Practices for Variable Declarations**

1. **Use const Where You Can**: This approach isn't always possible, especially when dealing with object properties. However, favor const for better code readability and to prevent accidental data mutations.

2. **Prefer let over var**: let adheres better to block-level scoping and offers more predictability in the code.

3. **Initialize at Declaration**: Although TypeScript allows initializations after declarations, it's best to declare and initialize variables simultaneously to improve code clarity and type safety.

4. **Prefer Type Annotations**: Explicitly specifying variable types can improve code readability. However, when the variable type is obvious from the initialization, type inference should suffice.
</details>


<details>
<summary>
43.<b> What are Interfaces in TypeScript and how do they work?</b>
</summary>

In TypeScript, an **interface** defines the structure and types of its members. It acts as a contract for the required properties and methods, ensuring that implementing classes or objects match this structure.

**Key Features of Interfaces**

**Type Consistency**: Objects that adhere to an interface's structure are considered compatible with it.
**Optional and Readonly Members**: Interfaces allow for optional attributes and readonly members with the ? and readonly keywords respectively.
**Call Signatures**: Interfaces can define method types, specifying function parameter and return types.
**Index Signatures**: Useful for specifying that an object can have any number of properties, all of a certain type.
Core Use-Cases
**Standardizing Objects**: Ensuring that disparate objects share a common structure for increased cohesiveness and ease of use.
**Contract Enforcement**: Enforcing property and method requirements on classes to reduce errors and improve maintainability.

**Code Example: Basic Interface**
Here is the TypeScript code:

```jsx harmony 
interface Point {
    x: number;
    y: number;
}
  
function printPoint(p: Point) {
    console.log(`Point coordinates: (${p.x}, ${p.y})`);
}

let pointA = { x: 3, y: 7 }; // This object matches Point's structure
let pointB = { x: 8 }; // This object is missing the 'y' property

printPoint(pointA); // Output: Point coordinates: (3, 7)
printPoint(pointB); // Compile-time error due to incorrect structure
```
</details>


<details>
<summary>
44.<b> Describe the Enum type and when you might use it.</b>
</summary>

The **Enum** is a data type that simplifies the representation and management of discrete, named values. It's a foundational tool to ensure **type safety** in TypeScript and a number of vital use-cases:

**Reducing 'Magic Values'**: When ensuring readability and preventing repetitive literal values, such as `1`, `2`, or `'red'`.
**Configuring Behaviour**: influencing functionalities sets of associated values, such as HTTP methods, ordering or customer types.
**Ensuring Type Safety and Efficiency**: The predefined set of valid members and a clear data type ensures that value assignments and operations are unequivocal and consistent.

**Core Components**
**Key**: a unique identifier, typically a number or string.
**Value**: Data associated with the key. If not provided, the key is used as the value.

**Standard, String, and Heterogeneous Enums**

**Standard Enum**: Every key and value are of the same data type, typically numbers.
**String Enum**: All keys and values must be strings, ensuring consistent data representation.
**Heterogeneous Enum**: Defines keys with both number or string values. However, due to the mixed-type nature of these enums, it's best to steer clear of them in most cases.

**Code Example: Standard Enum**
Here is the TypeScript code:

```jsx harmony 
enum HttpMethods {
  GET,
  POST,
  PUT,
  DELETE
}

const requestType: HttpMethods = HttpMethods.GET;

// ❌ This is not allowed due to type safety
// const requestType2: HttpMethods = 'GET';
```

In the example, the key `GET` is implicitly assigned the value `0`.

**Code Example: String Enum**
Here is the TypeScript code:

```jsx harmony 
enum MediaTypes {
  Image = 'image',
  Video = 'video',
  Audio = 'audio'
}

const selectedType: MediaTypes = MediaTypes.Image;

// ❌ This is not allowed due to type safety
// const selectedType2: MediaTypes = MediaTypes.Video;

// ✅ Accessing the value
const associatedText: string = MediaTypes.Image;

// ❌ This is not allowed due to type safety
// const invalidType: MediaTypes = 'image';
```
the Enum helps ensure the proper data type and its values.

**Pragmatic Use of Enums**
While Enums are a powerful tool for maintaining type safety, simplify associating related sets of values.

However, a consideration is that an Enum value can be inferred or forced to be of any key and underlying value type.

**Potential Downsides of Enums**
**Compilation Impact**: When used in a broader context, or in data structures like arrays or maps, TypeScript generates additional code to convert Enum keys to their associated values.
**Memory Usage**: Every usage of an Enum requires memory allocation for its value.
When a simple constant would suffice or if there's a need for a more dynamic relationship between keys and values, detailed types would be a better alternative.

</details>


<details>
<summary>
45.<b> How do you define and use a function in TypeScript?</b>
</summary>

When defining a **function** in TypeScript, you have the following fundamental components to consider:

**Function Signature**: Comprising the function's purpose, parameters, type, and return value.
**Function Body**: Containing the actual operation or series of steps the function will execute.


**Key Concepts**

1) **Function Declaration**

To declare a function, you specify its name, its parameter list, and its return type. If the function doesn't return a value, you set the return type to `void`.

Here is a code example:

```jsx harmony 

function greet(name: string): void {
    console.log(`Hello, ${name}!`);
}
```

2) **Function Expression**
You can also declare functions using expressions, which involve assigning functions to variables as values. This approach allows you to be more flexible, such as when you're using `callbacks`.

Here is an example:

```jsx harmony 
let greet: (name: string) => void;
greet = function(name: string): void {
    console.log(`Hello, ${name}!`);
};

```

3) **Optional and Default Parameters**

TypeScript supports both `optional` and `default` function parameters, enhancing the flexibility of your functions.

`Optional Parameters` are denoted by a `?` symbol after the parameter name.

Here is the code example:

```jsx harmony 

function greet(name: string, title?: string) {
    if (title) {
        console.log(`Hello, ${title} ${name}!`);
    } else {
        console.log(`Hello, ${name}!`);
    }
}
```

`Default Parameters` are when you assign a default value to a parameter:

Here is the code example:

```jsx harmony 
function greet(name = "Stranger") {
    console.log(`Hello, ${name}!`);
}
```

4. **Use Rest Parameters**
You can define a parameter as a "rest" parameter, which means the function can accept any number of arguments for that parameter.

Here is the code example:

```jsx harmony 

function introduce(greeting: string, ...names: string[]) {
    console.log(`${greeting}, ${names.join(", ")}!`);
}

introduce("Hello", "Alice", "Bob", "Carol");
```

5. **Function Overloads**

You can declare multiple function overloads to define a set of parameters and their return types for a single function. This feature is especially beneficial when the function's behavior logically varies based on different input types.

Here is the code example:

```jsx harmony 
function specialGreet(name: string): void;
function specialGreet(title: string, name: string): void;

function specialGreet(a: any, b?: any): void {
    if (b) {
        console.log(`Hello, ${a}, ${b}`);
    } else {
        console.log(`Hello, ${a}`);
    }
}

```

6) **Call Signature**
When using objects in TypeScript, you have the call signature to define the expected function structure for a specific method within the object.

Here is a code example:

```jsx harmony 
type Greeter = {
    (name: string): void
};

let welcome: Greeter;
welcome = function(name: string): void {
    console.log(`Welcome, ${name}!`);
};
```
</details>


<details>
<summary>
46.<b></b>
</summary>
</details>


<details>
<summary>
47.<b></b>
</summary>
</details>


<details>
<summary>
48.<b></b>
</summary>
</details>


<details>
<summary>
49.<b></b>
</summary>
</details>


<details>
<summary>
50.<b></b>
</summary>
</details>


<details>
<summary>
51.<b></b>
</summary>
</details>


<details>
<summary>
52.<b></b>
</summary>
</details>


<details>
<summary>
53.<b></b>
</summary>
</details>



<details>
<summary>
54.<b></b>
</summary>
</details>



<details>
<summary>
55.<b></b>
</summary>
</details>

<details>
<summary>
56.<b></b>
</summary>
</details>


<details>
<summary>
57.<b></b>
</summary>
</details>


<details>
<summary>
58.<b></b>
</summary>
</details>


<details>
<summary>
59.<b></b>
</summary>
</details>


<details>
<summary>
60.<b></b>
</summary>
</details>


<details>
<summary>
61.<b></b>
</summary>
</details>


<details>
<summary>
62.<b></b>
</summary>
</details>


<details>
<summary>
63.<b></b>
</summary>
</details>


<details>
<summary>
64.<b></b>
</summary>
</details>


<details>
<summary>
65.<b></b>
</summary>
</details>


<details>
<summary>
66.<b></b>
</summary>
</details>


<details>
<summary>
67.<b></b>
</summary>
</details>


<details>
<summary>
68.<b></b>
</summary>
</details>


<details>
<summary>
69.<b></b>
</summary>
</details>



<details>
<summary>
70.<b></b>
</summary>
</details>





<details>
<summary>
71.<b></b>
</summary>
</details>



<details>
<summary>
72.<b></b>
</summary>
</details>


<details>
<summary>
73.<b></b>
</summary>
</details>


<details>
<summary>
74.<b></b>
</summary>
</details>


<details>
<summary>
75.<b></b>
</summary>
</details>


<details>
<summary>
76.<b></b>
</summary>
</details>


<details>
<summary>
77.<b></b>
</summary>
</details>


<details>
<summary>
78.<b></b>
</summary>
</details>


<details>
<summary>
79.<b></b>
</summary>
</details>


<details>
<summary>
80.<b></b>
</summary>
</details>


<details>
<summary>
81.<b></b>
</summary>
</details>


<details>
<summary>
82.<b></b>
</summary>
</details>


<details>
<summary>
83.<b></b>
</summary>
</details>


<details>
<summary>
84.<b></b>
</summary>
</details>



<details>
<summary>
85.<b></b>
</summary>
</details>



<details>
<summary>
86.<b></b>
</summary>
</details>


<details>
<summary>
87.<b></b>
</summary>
</details>


<details>
<summary>
88.<b></b>
</summary>
</details>


<details>
<summary>
89.<b></b>
</summary>
</details>

<details>
<summary>
90.<b></b>
</summary>
</details>


<details>
<summary>
91.<b></b>
</summary>
</details>


<details>
<summary>
92.<b></b>
</summary>
</details>


<details>
<summary>
93.<b></b>
</summary>
</details>


<details>
<summary>
94.<b></b>
</summary>
</details>


<details>
<summary>
95.<b></b>
</summary>
</details>


<details>
<summary>
96.<b></b>
</summary>
</details>


<details>
<summary>
97.<b></b>
</summary>
</details>


<details>
<summary>
98.<b></b>
</summary>
</details>

<details>
<summary>
99.<b></b>
</summary>
</details>

<details>
<summary>
100.<b></b>
</summary>
</details>