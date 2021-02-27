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
