# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Functional Components

### Learning Objectives

*After this lesson, you will be able to:*

- Contrast class components with functional components
- Rewrite class components into functional components

---

## Components

Functional Components vs. Presentational Components

<aside class="notes">

**Talking Points**:

- So far, we have been building components using the `class` syntax.  As you have seen, this allows us to utilize changing values through state and build custom class methods. React **class** components also give us properties that we don't always need, namely state, methods like `setState`, and lifecycle methods (more about this later).

- Some components are purely presentational. They take props and render UI. As a React class, these components usually just contain a `render` method.

</aside>

---

### Building A Functional Component

As a class, we might have:

```javascript
class Name extends React.Component {
  render() {
    return (
      <div>
        Name: {this.props.firstName} {this.props.lastName}
      </div>
    )
  }
}
```

But with ES6, we now have:

```javascript
const Name = props => (
  <div>
    Name: {props.firstName} {props.lastName}
  </div>
)
```

<aside class="notes">

**Talking Points**:

- Rather than create them as classes, you can write them as functions. A React Functional Component takes the `props` object as its argument and returns JSX. Here's a very simple example.

- The whole declaration of `class`, `extends`, `React.component`, etc - it's all been replaced. We now just have the component name, an input for the `props`, and what is returned. Simplicity at its finest!

</aside>

---

### When should you use Functional Components, and when should you use Class Components?

<aside class="notes">

**Talking Points**:

- If (1) you don't need anything special (2) you are purely just returning JSX to render something use a functional component. But: If you need your component to be stateful - that is, if you need the ability to use `setState` to respond to changes -- use a class. If you need lifecycle methods - if you need to do something when the component mounts, or receives `props`, or unmounts -- use a class.

- And only if you _don't_ need any of those things -- use a Functional Component.

</aside>

---

## We Do: Functional Components Exercise


```javascript
import React from 'react';

const ListItem = props => (
  <div>
    <li>{props.doThis}</li>
  </div>
)

export default ListItem


```


<aside class="notes">

**Talking Points**:

- Now that we've learned about functional components, is there any place we can apply them?

- Look through the projects you've done so far. Are there any places you could use a functional component?

- Let's do one together. Open your to-do list project.

- Look at your `ListItem.js`. All it does is return JSX. This is prime functional component material.

- First, rewrite `ListItem.js` to be a functional component.

**Teaching Tips**:

- Students may not have been exposed to a one line return when using an arrow function.  Take a moment to make sure students understand what is happening here.

</aside>

---

### What's Different?


<aside class="notes">

**Talking Points**:

- All that has changed is that `ListItem` now looks much more like a function than a component. However, `ListItem` is still a component - it returns JSX of UI to be rendered to the virtual DOM - therefore, we still need to export it (so we can call it from `App.js`), and we still need the `import` statements - a React component won't work without React!

- What else in your projects can you change?

- Not only can the `ListItem` be converted into a functional component. The
entire `ToDoList` can be its own functional component as well.

</aside>

---

## You Do: Functional Components in the ToDo List



* Define as `const ToDoList` similar to `ListItem`.
* Import `ListItem` because it will render `ListItems`.
* Accept `props` like `ListItem`.
* Expect there something called `toDoItemArray` attached to props.
* Use `props.toDoItemArray.map(item, index)` to iterate over each item.
* Render `<ListItem>` components inside the map.
* Pass the proper properties (`doThis` and `key`) to the `<ListItem>` component


<aside class="notes">

**Talking Points**:

- Make a new file called `ToDoList.js` and have it look very much like the
`const ListItem` functional component above. It should have the 
properties listed here.

- The syntax of getting the mapping to work can be tricky. Notice that it must
be surrounded in curly braces, like the fruit list example that uses `.map()`
to generate a table.

</aside>
