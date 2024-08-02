
Tags: [[React]]

---
 
Why React and ReactDOM are a separate packages?

---

*React* is the Core Library responsible for defining and managing the components of the application. It provides mechanisms for creating and updating UI components in a declarative and efficient manner.

*ReactDOM* is a separate package that provides the bridge between React virtual DOM and the browser's actual DOM. It is responsible for rendering React components into the HTML DOM and handling events such as user input etc. It also exposes methods like `render()` that are used to render React components into the DOM.

---

React focuses on the core functionality of defining and managing components, while ReactDOM handles the rendering of those components into the browser DOM.
Separating these concerns allows React to remain framework-agnostic, meaning you can use it to build UI for various platforms.
Working beyond just web browsers, such as mobile apps with React Native or virtual reality experiences with React 360.
Meanwhile, ReactDOM specifically targets web development, providing the necessary functionality to interact with the browser environment.

React -> script writer (defining characters, designing scenes)
ReactDOM -> stage crew (building sets, arranging props, managing lighting etc.)