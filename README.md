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
  
 * Element is a plain object & also Once an element is created, it is never mutated.
 * Elements can contain other Elements in their props. 
 * Creating a React element is cheap
 
 `component`<br/>
 
 * component can be declared in several different ways
 * can be a class with a render() method
 * it can be defined as a function
 * it takes props as an input, and returns a JSX tree as the output:
 
