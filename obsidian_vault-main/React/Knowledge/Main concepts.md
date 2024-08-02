
Tags: [[React]]

---
 

***What is the virtual DOM?*** - It is a lightweight copy of the actual DOM  in memory. React uses it to improve performance by updating only the changed parts of the actual dom.

---

***What is the difference between class and functional components?*** - class components use ES6 classes and have additional features like state and life cycle methods, while functional components are simpler and are often used with hooks.

---

***How does React handle routing?*** - by using the React Router library, which provides a way to navigate between different views or pages in a React app.

---

***How does React handle code splitting?*** - React supports code splitting, by allowing split the code into smaller chunks that are loaded on demand, improving performance by reducing the initial bundle size.

---

***Explain the concept of refs in React*** - refs are used to access the DOM directly or to reference a React element. They provide a way to interact with the underlying DOM nodes in React.

---

***What is the significance of keys in React?*** - Keys are used to uniquely identify and differentiate between components in React. They help React to identify which items have changed, added, or removed.

---

***What is the significance of the key attribute in React lists?*** - The key attribute is used to uniquely identify elements in a list. It helps React efficiently update the DOM when the list changes.

---

***Explain the concept of lazy loading in React**** - it is a technique where components, modules, images etc. are loaded only when they are actually needed improving the load times. Fe. the target element on the bottom of the page will be loaded only after scrolling into some specific point of the page.

---

***What are state and props in React?*** - State is an internal data store that belongs to a specific component , and it can be changed over time. Props are properties passed to a component from its parent, and they are immutable.

---

***What is the difference between state and props?*** - Props make components reusable by giving them the ability to receive data from the parent component. State is private to the component. It is used to hold information about the component's current situation that may change over time. If it changes, the component is re-rendered with the updated state. 

---
14. **Explain the concept of context in React** - Context provides a way to pass data through the component tree without having to pass props manually at every level. Often used to share values like theme, auth status etc.
15. ***How prop drilling can be avoided in React?*** - by using context or state management libraries like Redux.
16. ***Explain the concept of error boundaries in React*** - Error boundaries are components that catch JS errors anywhere in their child component tree and log them, display a fallback UI, or take other actions.
17. ***Explain the concept of suspense in React*** - Suspense is a feature in React that allows components to "wait" for something before rendering, such as data fetching or code splitting.
18. **Explain the significance of the SuspenseList component in React** - SuspenseList is a component that allows developers to coordinate the loading of multiple components in a way that provides a better user experience.