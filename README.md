# ReactJs-Notes

### What is React ? 

 * React is an **open-source frontend JavaScript library** which is used for building user interfaces     especially for single page applications.
 * It is used for handling view layer for web and mobile apps.
 * React was created by **Jordan Walke**, a software engineer working for Facebook.
 * React was first deployed on **Facebook's News Feed** in 2011 and on **Instagram** in 2012
 
 ### What are the major features of React?
 
 * **VirtualDOM** instead RealDOM considering that RealDOM manipulations are expensive.
 * Supports **server-side rendering**.
 * Follows **Unidirectional data flow** or data binding.
 * Uses **reusable/composable** UI components to develop the view.
 
 ### What us JSX?
 
 * JSX is a XML-like syntax extension to **ECMAScript** (the acronym stands for **JavaScript XML**)
 * giving us expressiveness of **JavaScript along with HTML** like template syntax.
 
 ### What is meant by ECMAScript?
 
 * ECMAScript (**European Computer Manufacturers Association Script**) is a scripting language based on JavaScript.
 * ECMAScript is widely used on the World Wide Web especially for client-side scripting.
 
 ### Difference b/w Element and component ?
  
  `Element`<br/>
  
 * Element is a **plain object** & also Once an element is created, it is **never mutated**.
 * Elements **can contain other Elements in their props**. 
 * Creating a React element is cheap
 
 `component`<br/>
 
 * component can be **declared in several different ways**
 * can be a **class with a render() method**
 * it can be **defined as a function**
 * it takes **props as an input**, and returns a **JSX tree as the output**
 
 ### How to create components in React ?
  
  `Funtion Components`<br/>
  
 * Pure Javascript Funtion
 * that accept props object as first parameter and return React elements
 
 `Class Components`<br/>
 
 * You can also use ES6 class to define a component. 

### When to use a Class Component over a Function Component?

* component needs state or lifecycle methods then use class component otherwise use function component
* from React 16.8 with the addition of Hooks, you could use state , lifecycle methods and other features that were only available in class component right in your function component.

### What are Pure Components?

* **React.PureComponent is exactly the same as React.Component**
* except that it handles the shouldComponentUpdate() method for you.
* When props or state changes, PureComponent will do a shallow comparison on both props and state.
* the **component will re-render by default whenever shouldComponentUpdate is called.**

### What is state in React?

* **State of a component is an object that holds some information** that may **change over the lifetime of the component**.
* We should always **try to make our state as simple as possible** and minimize the number of stateful components.
* **State is similar to props**, but it is **private and fully controlled by the component**.
* **It is not accessible to any component other than the one that owns and sets it.**

![state](images/state.jpg)
