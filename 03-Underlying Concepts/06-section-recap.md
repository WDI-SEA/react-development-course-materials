# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Underlying Concepts: Section Recap



In this section, we dove deeper into React. Here's what we covered:

---

## Component Lifecycle

React class components have lifecycle methods that are invoked at certain stages of a component's "life" on the DOM. Some of the lifecycle methods you'll use frequently are:

  - `constructor()`: Initializes state, binds methods.
  - `componentDidMount()`: Makes AJAX requests, gets DOM refs, binds event listeners, sets `state` if necessary.
  - `componentWillUnmount()`: Unbinds event listeners, performs other clean-up.
  - `componentDidUpdate()`: Updates `state` based on changes in components.
  - `render()`: Returns markup/UI.

---

## Unidirectional Data Flow

In React, data flows from the top down. Keep your data higher in your component tree so it's available to the sibling/children components that need it.

---

## Declarative vs. Imperative Programming

  - Imperative programming is a more classical 'line-by-line' approach to programming.
  - Declarative programming expresses the logic of a computation without describing its control flow.
