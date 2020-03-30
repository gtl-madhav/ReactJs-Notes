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

### -- Summery Of Performace issues. --

1. Virtual DOM - also update entire sub tree
2. To-Do Example
3. Chrome Extension
4. Why did you update Library
5. shouldComponentUpdate method
6. Twitter Example 
7. PureComponent
8. Single Character Search Example 
9. Immutable.js
10. PWA - React - Bundle size 
11. Webpack bundle analyzer
12. Gzip compression
13. Code Splitting 
14. Lazy-Load 
15. Pinterest Example 
16. CommonChunkPlugin web pack 
17. SSR server side rendering with Next.js
18. Housing.com example 
19. Lazy Login Image 
20. Pinterest for Lazy loving image
21. React Lazy-load library 
22. Long List with 10000+ date
23. Scrolling make UI memory issues 
24. React Virtualised List - just like recycler view in android 
25. correct keys for components
26. React - Redux based performance issues 
27. RESELECT library - for Redux Based React Apps. handling the complex rendering operations.
28. Using Immutable.js to further optimize performance issues in Redux based React apps
29. mutable data structures could results in unnecessary data copying due to a nested Redux state tree
30. immutating data structures in Redux based React app ensures that all operations of app returns a newer version of data structure and keep the original data structure intact instead of updating it.


### Advance Performance issues Discusstion and solution 

## How UI is rendered in React? (Advantage)

 * In React, your UI is rendered by updating something called as DOM (Document Object Model).
 * In basic layman terms, DOM resembles like a tree like structure of objects and nodes.
 * The React DOM knows how to render a page but it is not so intelligent to keep track of each node and components which are updating.
 * let’s say you have a list of 10 items on your SPA (Single page Application) and you have to update one of them when your user interacts with UI. With DOM, you will end up updating all the components as entire list will get re rendered.
 * That’s where the concept of Virtual DOM comes into play. The Virtual DOM is React’s local copy of the HTML DOM.
 * When user interacts with UI, React would create a copy in the form of Virtual DOM and updates the UI after comparing the real DOM with virtual DOM. In this way, the item which needs to be updated will update without affecting other items.
 
##  What’s BAD about Virtual DOM? (Disadvantage)

 * So, in simple words -> lets say you have a tree and In tree you have Root(A) - Child (B) - Child (C,D) - now think you want to update the C or D component from your child element .. React will render Entire Child called B.
 * Limitation of react and that is why causing big performance problem. 
 * Redundant processing in components that do not update the DOM
 * Diff Algorithm keeps on updating leaf nodes that do not need to be updated
 * Heavy CPU computation due to Diff algorithm updating components
 * **Todo Example** 
 * This is where **React performance tools** `chrome extension` would comes handy for your application. At present, these tools only work blazingly fast with React version 16. "https://chrome.google.com/webstore/detail/react-performance-devtool/fcombecpigkkfcbfaeikoeegkmkjfbfm?hl=en"
      * https://developers.google.com/web/tools/chrome-devtools/
 * Detecting unnecessary rendering of components by using **“Why did you update”** library
      * https://github.com/maicki/why-did-you-update
 * Implementing **shouldComponentUpdate** for preventing unnecessary renders
 * **Twitter Example** where we are just liking a Twite but entire UI is rendered again (after apple this new method 10X faster perfomance measure by Twitter.)
 * Not every case comes under - shouldComponentUpdate - so apply it very nicely
 * Improving performance due to unnecessary renders **using PureComponent**
 * **Single Cherecter Text search Example.** 
 * While **defining shouldComponentUpdate method**, it is your job to **tell React if component needs to be re rendered** to reflect state and new properties.
 * An ideal way to use shouldComponentUpdate is to make it more lightweight as possible since it is called for every single component.
 * at **some point you’ll want to do comparison** with the **new and old props**. However, the comparison like this is not straightforward. **(immutable.js)**
 * This is where immutable data comes into picture
 * By definition, immutable data structures never change
 * Immutable data allows you to compare direct object references instead of doing deep-tree comparisons
 * **This makes a React app faster.**
 
### Identifying problematic bundles for a React based PWA

 * optimizing the bundle size of React app deals with identifying the problematic chunks of code in your production build.
 * If you are using webpack for easy bundling in React, then you can use Webpack Bundle Analyzer plugin for analyzing your build dependencies.
 * **Pinterest were able to identify tons of duplicate code in their build with the help of Webpack bundle analyzer plugin.**
 * chunk to their main chunk which decreased the size of all lazy loaded chunks by 90 %.
 * Compression-webpack-plugin, Dedupe-plugin, Uglifyjs-plugin, Ignore-plugin -- **Other Plugin for analysis.**
 * Optimizing the Javascript bundle with **Gzip compression** -->  bundle size to a 20% to 25%.
 
### Optimizing the app loading time further with Code splitting

 * only load the code which your user needs upfront.
 * case of single page apps (SPA)
 * no particular reason to load the code that comprises an admin panel when you want your user to view a landing page.
 * **Code-splitting your app can help you “lazy-load” just the things that are currently needed by the user, which can dramatically improve the performance of your app**
 * utilizing code-splitting technique -> Pinterest take down the size of their bundles from 650KB to 150KB. & their app loading time from 23 seconds to 6.5 seconds.
 * If you are using **webpack**, you can split your code into multiple files by using **CommonsChunkPlugin.**
 
### React performance with SSR

 * `Bad SEO` --> Since the **javascript-related content is rendered client-side,search engine won’t be able to index them as all they could see a blank page which relates to the negative SEO.** -- GOOGLE DOES THIS NO PROBLEM FOR GOOGLE
 * `Slow app loading time` --> When the **application loads initially**, there is **no cache of JavaScript in the browser**.If the application is big, the time taken to initially load the application will also be huge.
 * for search engines other than Google then it makes a lot of sense for you to go with **Server side rendering and build an Isomorphic React app.**
 * In server-side-rendering, the JavaScript-related content is rendered from the server initially.
 * **SSR helped the engineering team at Housing.com serve the meaningful content to users 3 seconds faster on normal 3G networks as compared to client-side rendered app.**
 * But implementing SSR in React comes with lot of code-complexity and cost of setting it up is huge considering the requirement of good servers such as Node.js.
 * if you really want to **improve your app’s loading speed**, then you can **implement SSR with Next.js** which will save you a lot of time that goes into setting up the servers for SSR.

### Improving the app’s loading time by lazy loading Images

 * loading only the necessary code upfront which greatly improves app load speed.
 * **what about Images?**
 * Images are the heaviest resources that your user may never see until a web page is fully loaded. 
     * `Data Wastage:` Loading Images un-necessarily leads to heavy usage of data which is complete waste considering that your user can’t see them properly.
     * `Unnecessary consumption of device resources and battery:` After an Image gets downloaded from the server, the browser must decode it and render the content to UI which requires heavy consumption of device resources and battery.
 * In order to improve app-loading time, a rule of thumb is to load the images at the moment of need instead of loading them while the app’s page is loading. This is referred to as Lazy loading of Images.
 * Pinterest used a progressive lazy loading technique for images in their Progressive Web App.
 * Pinterest used a **placeholder initially** at the time of Page load. The image appear as blurr at the initial load but it loads completely once the page is fully loaded.
 * Lazy Loading of Images in a React app can be implemented by using **React Lazyload library.**
 
 ### Rendering a big list of data
 
  * React which is supposed to render elements on scrolling, you might experience that your UI might lag a bit after you scroll down fast till 1000 items.
  * Here scrolling up works great, but when you start scrolling down, everything goes Topsy turvy.
  * When you scroll down fast, you are doing too much of rendering between components which makes the UI sluggish
  * **Example** Ever experienced boredom when your teacher makes your lecture long and explained too much of stuffs at a time? This is because during long sessions, hundreds of messages in the form of information gets exchanged between tutor and students due to which students (say components in the example) feels it hard to consume. As a result they gets bored (which means components gets re-rendered) and tutor starts complaining (which means UI gets sluggish).
  * **Optimizing list rendering with React Virtualized List**
  * Virtual rendering comes into play. Instead of rendering the whole bunch of components, it lets you render just 30 components. Or 40, or 10.
  * at the end of the day you will render a small subset of the components. This gives you a big performance boost
  * **React Virtualized list is a library** that takes virtual rendering technique into account. 
  * **Optimizing React list performance by using correct keys for components**
  * React uses the Key attribute to decide which elements can be reused for the next rendering phase. These keys are important for updating elements in dynamic lists.
  * React does this updation by comparing the keys of the new element with the keys of the previous element.
  * it might also render components having a new key and unrender the components which have keys that are not used anymore.
  * I have seen that most developers wrongly assumes index of an item as the key while rendering a list which is why they ran into performance issues such as:
  * **Unnecessary re-renders in list**
  * **Unwanted bugs which may make an UI unresponsive while scrolling** 
  * Using the key attributes in your list will help you out maintaining the consistent performance with your lists.
  * do remember that your key value should be unique for every single component in the list.
  * use Key={ } wisely while implementing list in React.
  * **React performance tips – React-redux based app performance Optimization**
  * When you are using **Redux**, your app’s **components which have subscribed to Redux** store **gets re-rendered unnecessarily** which slows down your app with major fractions of time.
  * **In Yahoo’s case**, they still faced the performance lag in their Redux-based React app even after optimizing the component rendering with shouldComponentUpdate.
  * **Optimizing Redux based React apps with RESELECT**
  * **RESELECT is a library** which should be used in your Redux based React apps when you have your higher order components handling the complex rendering operations.
  * **Yahoo experienced a significant improvement in performance of their Data Analytics tool after using RESELECT.**
  * Using **Immutable.js to further optimize performance issues in Redux** based React apps
  * **There is even a benchmarking study which demonstrates that using Immutable.js in Redux-react app can improve application performance in considerable manner**
  * **study compares two large-lists (10,000 items each) in which one is mutable and other is immutable. When the performance of both the lists were analyzed, the immutable list was said to be 4x performant than non-immutable one.**
  * Using mutable data structures could results in unnecessary data copying due to a nested Redux state tree which consumes lot of device memory and slows down the React app performance.
  * On the other hand, immutating data structures in Redux based React app ensures that all operations of app returns a newer version of data structure and keep the original data structure intact instead of updating it.
  
  `Source` :: https://www.simform.com/react-performance/ </br>
  `Source`:: https://www.simform.com/websites-use-react/ </br>
  `Source`:: https://www.simform.com/use-nodejs-with-react/ </br>
