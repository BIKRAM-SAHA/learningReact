[Back to Content](../README.md)


# What is React?
- ReactJS is a declarative, efficient, and flexible JavaScript library for building reusable UI components 
- It is an open-source, component-based front end library responsible only for the view layer of the application

# Why React?
- <details>
  <summary>Uses VirDOM</summary>
  
  - improves the performance of the app, as it only changes individual DOM elements instead of reloading complete DOM every time
  - ISSUE: 
    DOM is an object which is created by the browser each time a web page is loaded. It dynamically adds or removes the data at the back end and when any modifications were done, then each time a new DOM is created for the same page. This repeated creation of DOM makes unnecessary memory wastage and reduces the performance of the application.
  - HOW REACT SOLVES IT: 
    ReactJS allows you to divide your entire application into various components. ReactJS still used the same traditional data flow, but it is not directly operating on the browser's DOM immediately; instead, it operates on a virtual DOM, i.e. rather than manipulating the document in a browser after changes to our data, it resolves changes on a DOM built and run entirely in memory. After the virtual DOM has been updated, React determines what changes made to the actual browser's DOM. The React Virtual DOM exists entirely in memory and is a representation of the web browser's DOM. Due to this, when we write a React component, we did not write directly to the DOM; instead, we are writing virtual components that react will turn into the DOM.
</details>

- <details>
  <summary>Modular Code structure</summary>
  
  - It uses component and data patterns that improve readability and helps to maintain larger apps.
</details>

- We can use ReactJS on the client and server-side as well as with other frameworks.

## Features of React:
- <details>
  <summary>JSX</summary>
  
  - A Javascript syntax extension standing for JavaScript XML.
  - extends the ES6 so that HTML like text can co-exist with JavaScript react code.
  - not necessary to use but makes the workflow faster to code and easier to understand.
</details>

- <details>
  <summary>Components</summary>
  
  - ReactJS is based on concept of Components.
  - Any react application is made of multiple Components that are reuseable and have their own logic and controls.
</details>

- <details>
  <summary>One-way Data Binding</summary>
  
  - React to designed to have one-directional data flow (i.e. one-way data binding) which gives better control throughout the application
  - if data is to flow to other direction it needs additional feature as in react Components are supposed to be immutable and data inside them cannot be changed.
  - Flux is a pattern that helps the data to be unidirectional leading to more flexibilty and increased efficiency.
</details>

- <details>
  <summary>Virtual DOM</summary>
  
  - A virtual DOM object is a representation of the original DOM object that works like a one-way data binding.
  - On a modification the whole UI is re-rendered in the VirDOM and the differences between previous DOM reresentation and the new one are checked
  - After that React updates only the things in Real DOM that have actually changed
  - makes the application faster.
</details>

- <details>
  <summary>Simplicity</summary>
  
  - use of JSX makes the app easy to code and understand
  - use of component based approach makes the code reusable.
</details>

- <details>
  <summary>Performance</summary>
  
  - React is known for its performance
  - the management of VirDOM helps the cause
  - The DOM is a cross-platform and programming API which deals with HTML, XML or XHTML. The DOM exists entirely in memory. Due to this, when we create a component, we did not write directly to the DOM. Instead, we are writing virtual components that will turn into the DOM leading to smoother and faster performance.
</details>

- <details>
  <summary>SEO Friendly</summary>
  
  - The search engines generally having trouble in reading JavaScript-heavy applications.
  - React solves this as it can run in the server, and the VirDOM actually returns the browser a regular web page.
</details>

# React vs Angular

| | AngularJS |	ReactJS |
|---|---|---|
| Author | Google | Facebook Community |
| Developer	| Misko Hevery |	Jordan Walke |
| Initial Release |	October 2010 | March 2013 |
| Language	| JavaScript, HTML	| JSX | 
| Type	| Open Source MVC Framework	| Open Source JS Framework | 
| Rendering	| Client-Side	| Server-Side | 
| Packaging	| Weak	| Strong | 
| Data-Binding	| Bi-directional	| Uni-directional | 
| DOM	| Regular DOM	| Virtual DOM | 
| Testing	| Unit and Integration Testing | 	Unit Testing | 
| App | Architecture	| MVC	Flux | 
| Dependencies	| It manages dependencies automatically	| It requires additional tools to manage dependencies | 
| Routing	| It requires a template or controller to its router configuration, which has to be managed manually |	It doesn't handle routing but has a lot of modules for routing, eg., react-router | 
| Performance	| Slow	| Fast, due to virtual DOM | 
| Best For	| It is best for single page applications that update a single view at a time | 	It is best for single page applications that update multiple views at a time | 


# React vs Vue

| |	React |	Vue |
|---|---|---|
| Definition | React is a declarative, efficient, flexible, open-source JavaScript library for building reusable UI components. |	Vue is an open-source JavaScript library for building reusable user interfaces and single-page applications. |
|	History	|	It was created by Jordan Walke, a software engineer at Facebook. It was initially developed and maintained by Facebook and later used in its products like WhatsApp & Instagram. Facebook developed React in 2011 for the newsfeed section, but it was released to the public on May 2013.	|	Vue was created by Evan You, a former employee of Google worked on many Angular projects. He wanted to make a better version of Angular, just extracting the part which he liked about Angular and making it lighter. The first release of Vue was introduced in February 2014. |	
|	Learning Curve |	React is not a complete framework, and the more advanced framework must be looked for the use of third-party libraries. It makes the learning of the core framework not so easy. It adds some complexity to the learning curve as it differs based on the choices you take with additional functionality.	|	Vue provides higher customizability, which makes it easier to learn than Angular or React. Vue shares some concepts with Angular and React in their functionality. Hence, the transition to Vue from Angular and React is an easy option. Also, the official documentation is well written and covers everything the developer needs to build a Vue app. |	
|	Preferred Language |	JavaScript/JavaScript XML	|	HTML/JavaScript |	
|	Size	|	The size of the React library is 100 kilobytes (approx.).	|	The size of the Vue library is 60 kilobytes (approx.). |	
|	Performance	|	Its performance is slow as compared to Vue.	|	Its performance is fast as compared to React. |	
|	Flexibility	|	React provides great flexibility to support third-party libraries.	|	Vue provides limited flexibility as compared to React. |	
|	Coding Style	|	React uses JSX for writing JavaScript Expression instead of regular JavaScript. JSX is similar to HTML code within the JavaScript expressions. React takes everything as Component, and each component has its own lifecycle methods.	|	Vue coding style is little similar to Angular. It separates HTML, JS, and CSS as like web developers have been used to the web development scenario for years. But, it also allows using JSX if you prefer. Vue's take of the component lifecycle more intuitive than React's. |	
|	Data Binding	|	React supports one-way data binding. The one-way data binding refers to a single source of truth. React flows in a single direction, and only the model can change the app's state.	|	Vue supports both one-way and two-way data binding. The two-way data binding is a mechanism where UI fields are bound to model dynamically. If the UI components change, model data is also changed accordingly. |	
|	Tooling	|	React has great tooling support. It uses third-party CLI tool (create-react-app), which helps to create new apps and components in React Project. It has excellent support for the major IDEs.	|	Vue provides limited tooling support as compared to React. It has a Vue CLI tool, which is similar to the create-react-app tool. It gives supports for major IDEs but not as good as React. |	
|	Long Term Support	|	It is suitable for long term supports.	|	It is not suitable for long term support. |	

[Next](../Setup_Environment/README.md)

Question1: How react updates the DOM (in detail)?

https://reactjs.org/docs/reconciliation.html#recursing-on-children