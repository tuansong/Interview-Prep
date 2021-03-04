# Interview Prep
## _The interview preparation with Tutuka on 5th Mar_


In this document we will focus on: 
- Javascript core
- React JS
- Vue Js
- Node Js
- MySQL and ColdFusion

## #1-Javascript core 

- Variable
- Datatype
- Object, Prototype, Classes, OOP 
- ES6
- Arrow function, callback
- Promise/ Async&Await
- Prototype, Classes, OOP 

**1/ Var, let, const**
    `var` declarations are globally scoped or function scoped while `let` and `const` are block scoped.
    `var` variables can be updated and re-declared within its scope; `let` variables can be updated but not re-declared; `const` variables can neither be updated nor re-declared.
    
**2/ Javascript dataType**
    Primitive data type: `String, Number, Boolean, Null, Undefined`
	Non-primitive data type: Object ( It could be Array )
	
**3/ Strict mode**
It helps you write a clean code, prevent error from using undeclared variables. ( > ES5 )

**4/ Everything about Object**
In Javascript `this` keyword refer to the object its belong to
Mostly everything in JS is a object 
Every Object have Properties, Methods, getter & setter, constructor, prototypes

Constructor:
+ Sometimes we need a "blueprint" for creating many objects of the same "type"
+ The way to create an "object type", is to use an object constructor function.
+ egs:
    ```js
    function Person(first, last, age, color) {
      			this.firstName = firstName; 
      			this.lastName = lastName;
      			this.age = age;
      			this.eyeColor = color;
      			this.changeName = function (name) {
       				this.lastName = name;
      			};
    		}
    const Me = new("song", "tran", 25, "tan")		
    ```
Getter and setter is the way to retrieve and update the properties in object 

All JavaScript objects inherit properties and methods from a prototype.

**5/ ES6**
Some of the new features of ES6 are:
- Support for constants (also known as “immutable variables”)
- Block-Scope support for both variables, constants, functions
- Arrow functions:
-- It close over "this" keyword
-- They cannot be used as constructors
- Export and import
- Spread & Rest Operators:
--Spread: Use to split up array elements or object properties:
--egs: cosnt oldArray = [1,2,3]. const newArray = [...oldAray, 4,5]
--Rest: use to merge a list of function argument into array. Egs: `function filterArgs( ...args ) { return args.filter( el => el === 1)`;
- Destructuring: Easily extract array elements or object properties and store them in variable
-- egs: `const numbers = [1,2,3,5] . const [ first, second ] = numbers`
- Classes
```js
    class Human {
        constructor() {
            this.gender = 'male';
        }
        printGender() {
            console.log(this.gender);
        }
    }
    
    class Person extends Human { //Person inherit from Human
        constructor(){
            super();            //Must add super function
            this.name = 'Max';
            this.gender = 'female' // gender can be override
        }
        printName() {
            console.log(this.name)
        }
    }
```



**6/ Callback, Promise, Async&Await**
Callback: 
A callback is a function passed as an argument to another function
This technique allows a function to call another function
A callback function can run after another function has finished

Promise ( ES5 ):
- A promise is an object that may produce a single value some time in the future
- It maybe in one of possible state: fullfilled, rejected, pending
- We can attach callback to handle the fullfilled value or the reason for rejection
- 


Async & Await ( ES6 ):
Async functions are a combination of promises and generators, and basically, they are a higher level abstraction over promises. Let me repeat: async/await is built on promises.


**6/ OOP in javascript**
https://www.youtube.com/watch?v=pTB0EiLXUC8
- Capsulation: using this we group related variable and function together so they will become properties and methods of that object => Reduce complexicty & increase reusability 
- Abstraction: Hide the the detail and complexicty and show essential => Reduce complexicy & reduce impact of change
- Inheritance: Eliminate reduncdant code 
- Polymophysm: Refactore ugrly code 
- 

Memory trick:  "Oops I ate A PIE"  


A - Abstraction
P - Polymorphism
I - Inheritance
E - Encaspulation
## #2-React
**1/ What is React**
React is a Open Source Frontend Library which is used for buliding user interface specially SPA. It's used for handling view layer for web and mobile
**2/ Major features of React**
- It uses VirtualDOM instead of RealDOM
- Support server side rendering
- Use reusable and composable UI component to develop the view


**3/ What is JSX**
JSX is XML like systax. It mostly look like HTML. It's used with React to describe what the UI should look like

**4/ How to create a component?**
There is two type of component: Function component and Class component ( they also knows as statefull and stateless component )
If component needs `state` or `lifecycle` then use class component otherwise use function component
Pure component will handle `shouldComponentUpdate()` for you
**5/ What is state?**
State like component data. It's used for internal communication inside 
it is private and fully controlled by the component
**6/ What is props?**
Props are input to component. It's naming convention is similar like HTML tag attribute. They are passed down from parent to childrent component.
**7/ What is virtual DOM?**
Whenever data change, the entire UI is update in virtual DOM. Then the difference between previous DOM and new one is calculated. After that the real DOM only update only the thing that actually updated
**8/ React lifecycle**
![alt lifecycle](https://github.com/sudheerj/reactjs-interview-questions/raw/master/images/phases16.3.jpg)

- getDerivedStateFromProps: Invoked right before calling render() and is invoked on every render. This exists for rare use cases where you need derived state. Worth reading if you need derived state.
- componentDidMount: Executed after first rendering and where all AJAX requests, DOM or state updates, and set up event listeners should occur.
- shouldComponentUpdate: Determines if the component will be updated or not. By default it returns true. If you are sure that the component doesn't need to render after state or props are updated, you can return false value. It is a great place to improve performance as it allows you to prevent a re-render if component receives new prop.
- getSnapshotBeforeUpdate: Executed right before rendered output is committed to the DOM. Any value returned by this will be passed into componentDidUpdate(). This is useful to capture information from the DOM i.e. scroll position.
- componentDidUpdate: Mostly it is used to update the DOM in response to prop or state changes. This will not fire if shouldComponentUpdate() returns false.
- componentWillUnmount It will be used to cancel any outgoing network requests, or remove all event listeners associated with the component.
- 
**9/ Children prop**
Children is a props `this.props.children` that allow you to pass components as data to another component

**10/ What is the purpose of using super constructor with props argument**
A child constructor can not make use of `this` reference until `super()` method has been called. The main reason of passing props to the `super` parameter is to access `this.props` in your child constructor

**10/ What is Hooks**
Hooks is a new feature ( React 16.8 ) that lets you use state and another features without writing classes

**11/ Redux?**
Redux is predicable state container for Javascript apps based on Flux design parttern
Core Principle of Redux:
- Single source of truth: State of your whole application stored in an object tree with single store. It easy to keep track and debug
- State is read only: The way to change state is emit an action 
- Changes are made with pure function: Reducers just pure functions

## #3-Node JS
**1/ What is Node?**
Node is a server side scripting which use to build scalable program
Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.

**2/ How node works?**
Node.js works on a v8 environment, it is a virtual machine that utilizes JavaScript as its scripting language and achieves high output via non-blocking I/O and single threaded event loop.

5) Where can we use node.js?

Node.js can be used for the following purposes.

Web applications ( especially real-time web apps )
Network applications
Distributed systems
General purpose applications
6) What is the advantage of using node.js?

It provides an easy way to build scalable network programs
Generally fast
Great concurrency
Asynchronous everything
Almost never blocks
7) What are the two types of API functions in Node.js ?

The two types of API functions in Node.js are

Asynchronous, non-blocking functions
Synchronous, blocking functions

10) Why Node.js is single threaded?

For async processing, Node.js was created explicitly as an experiment. It is believed that more performance and scalability can be achieved by doing async processing on a single thread under typical web loads than the typical thread based implementation.

5) What is ‘Callback’ in node.js?

Callback function is used in node.js to deal with multiple requests made to the server. Like if you have a large file which is going to take a long time for a server to read and if you don’t want a server to get engage in reading that large file while dealing with other requests, call back function is used. Call back function allows the server to deal with pending request first and call a function when it is finished.



## #4-Vue JS
**1/ What is Vue?**
Vue is open source javascript framework for building user interface

**2/ Major feature of Vue**
- Virtual DOM: Similar like React JS
- Component: We can create reusable custom component like React 
- Template: Where to define HTML with Vue instance Data
- Vue Js is lightweight library compare to another

**2/ Vue Lifecycle**
![alt lifecycle](https://github.com/sudheerj/vuejs-interview-questions/raw/master/images/vuelifecycle.png)

i.Creation( Initialization ): Creation hoooks allow you to perfom action before your component has been added into the DOM. This hook run during server side rendering:
- a: beforeCeated 
- b: Created
 
ii.Mounting (DOM insertion): They allow you to access your component immediately before and after first render 
- a: beforeMounted
- b: Mounted

iii.Updating(Diff and re-render) Updating hooks are called when your reactive property used by your component change or something else causes it to re-render
- beforeUpdate
- updated

iv.Destruction(Teardown) They allow you to perfome action when you component is destroyed
- beforeDestroy
- destroyed


## #5-My SQL
**1/ What is SQL?**
SQL is a open source database management system. It's reliable, fast and easy to use

**2/ technical features of MySQL?**
- Multithread SQL server
- Diference backend
- wild range of programing interface
- Adminstration tool

**1/ Default port of My SQL?**
default port is 3306

- The SQL SELECT Statement
The SELECT statement is used to select data from a database.

The data returned is stored in a result table, called the result-set.

- The SQL INSERT INTO Statement
The INSERT INTO statement is used to insert new records in a table.

- The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.

- The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.

- SQL INNER JOIN Keyword
The INNER JOIN keyword selects records that have matching values in both tables.


## #6-Cold Fusion
Cold fusion is a development framework by Adobe which provive an easy way to connect statics HTML page to database. It completely written in java

**1/ Datatype?**
Integers - they are used to store whole numbers.

Real Numbers - they are the floating-point numbers.

Strings - They are used to store a sequence of letters, symbols, or characters.

Booleans - They are "true" or "false" values.

Date-time - They are the data or time values.

Lists - It consists of multiple strings separated by a delimiter.

Arrays - It is a complex data-type. Some other types present in Coldfusion are Structure, queries, binary, and object.

**2/ variable scope?**
Variables - Variables are available only during the execution of the template.

URL - URL variables are available only for the current request.

Form - Form variables are only available for the current request.

CGI - CGI variables are available only for the current request.

Query - The data stored in the pointer are available for the current request.

Server - The server scope is available across all the requests until the server shuts down.

Application - The application variables are used by all the connected clients for current applications.

Session - The session scope is available only to the current session and can persist until the termination of the server or application.

Request - The data in this scope is available to the current request.

Arguments - This scope is mutually exclusive with the local function scope.

Attributes - This scope is available during the lifespan of the custom tag.

Local - This scope is mutually exclusive to the argument scope.

**2/ Aplication.cfm**
Contain set of codes that we want to execute on every page of aplication 
Application.cfm file can be used for setting application name, enabling and disabling sessions, Set timeouts, storing client variables, defining application global settings and much more.
