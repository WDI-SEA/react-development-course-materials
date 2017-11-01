### This is Quiz 3. It comes after the Immutable Data Types lecture.
- It covers functional components, component lifecycle, ES6, and unidirectional flow.

**Notes**:
- [The link to quiz 3 is here](https://ga-instruction-sandbox.herokuapp.com/?lessonURL=https://ga-instruction.s3.amazonaws.com/json/REACT/unit-3/U3L6.json). This is the link you give to students.

- At the end of the quiz, there is a link to [this review guide](../../../react-review-guides/blob/master/unit-3-react-review-guide.md). Students will see this in the quiz slides; you don't need to share the link.

### Questions:
- Answers with an asterisk are correct.


_Prompt*_: Does state ever get passed back to a parent component?


_Choices:*_

1. Yes
2. No *


_Explanation*_:  Unidirectional flow means that props and state only get passed one way - from parents to children.

----------------------------------

_Prompt*_: Which are the broad categories of component lifecycle? Choose all that apply.

_Correct Response*_:  Correct!

_Incorrect Response*_:  Not quite - there are three categories: Mounting, Updating, and Unmounting.


_Choices:*_

1. Mounting *
2. Updating *
3. Unmounting *
4. Constructing
5. None of the above.

-----------------------------------

_Prompt*_: Which of the below lines will throw an error? Choose all that apply.

```js
const dessert = {
  muffins: 'blueberry',
  mochi: `chocolate`
}

dessert.mochi = 'green tea'

function eatDessert() {
  const forMe = 'all of them!'
  if (true) {
    var forMe = 'Just the mochi'
    return forMe
  }
  return forMe
}

const bake = desserts => desserts * desserts

```

_Correct Response*_:  Correct! `const` is immutable and cannot be reassigned - but that is only the reference itself, so `mochi` can be reassigned with no issue. However, as `var` is scoped to the nearest parent, it essentially is trying to reassign `forMe` - a no go!

_Incorrect Response*_: Not quite. `const` is immutable and cannot be reassigned - but that is only the reference itself, so `mochi` can be reassigned with no issue. However, as `var` is scoped to the nearest parent, it essentially is trying to reassign `forMe` - a no go!


_Choices:*_

1. `dessert.mochi = 'green tea'`
2. `var forMe = 'Just the mochi'` *
3. `const bake = desserts => desserts * desserts`
4. None of them.

-----------------------------------

_Prompt*_:  Is the following code valid?

```js
const paella = ingredients => ingredients.map(paellaMe => paellaMe.toLocaleLowerCase())
const isCooked = cooked => {cook: cooked}
const eatBreakfast = pancakes => {
  this.food = 'Knife please?'
  return this.food
}
```

_Choices:*_

1. No - you cannot embed arrow functions.
2. No - `cook: cooked` must be wrapped in parentheses. *
3. No - `this` must be bound.
4. Yes

_Explanation*_: Right - object literals must be wrapped in parentheses. It should be `const isCooked = cooked => ({cook: cooked})`


----------------------------------

_Prompt*_: Why isn't this functional component defined properly? Select all that apply.

```js
const Sports = props.favorites => (
  <h1>
    I like {favorites.soccer} and {favorites.cricket}
  </h1>
)
```


_Correct Response*_: For functional components, the props are passed in like variables to a function - so it would simply be `favorites`, not `props.favorites`.

_Incorrect Response*_: Not quite. For functional components, the props are passed in like variables to a function - so it would simply be `favorites`, not `props.favorites`.



_Choices:*_

1. It should be `const Sports = favorites`, without the `props` *
2. It should be `{props.favorites.soccer} and {props.favorites.cricket}`
3. The JSX needs to be wrapped in a `<div>` tag.
4. It's defined correctly.


-----------------------------------

_Prompt*_: What function would this line of code go in?

`this.findPanda = this.findPanda.bind(this)`

_Choices:*_

1. `componentWillMount`
2. `componentDidMount`
3. `componentWillReceiveProps`
4. `constructor` *

_Explanation*_: When a method is "bound" to a component, it means that, when the method is invoked, `this` will refer to the component and not to the context that invoked the method. This binding is declared in the `constructor()` function.

----------------------------------

_Prompt*_: In React, components' state and props are both treated as immutable.

_Choices:*_

1. True *
2. False

_Explanation*_:  Right! In React, props are immutable - they are passed in to the component. State is also immutable - using setState does not actually directly mutate the state, but instead returns a fresh copy of the state (with a new reference) with the updated data.

-----------------------------------

_Prompt*_:  Applying ES6, what could change here? Choose all that apply.

```js
/*1*/ var ocean = "Pacific"
/*2*/ var swimming = {ocean: ocean,}
/*3*/ var greeting = 'Let us go in the ' + swimming + ' ocean.'
```


_Correct Response*_: Right - We can use template literals and object literal shorthand to simplify this, as well as declaring variables that won't change with `const`.

_Incorrect Response*_: Not quite. We can use template literals and object literal shorthand to simplify line 2, as well as declaring all the variables that won't change with `const`.


_Choices:*_

1. Line 2 could be `var swimming = {ocean,}` *
2. Line 3 could be `var greeting = 'Let us go in the {swimming} ocean.'`
3. Line 3 could be `var greeting = 'Let us go in the ${swimming} ocean.'` *
4. The variables could be declared as `const` *

----------------------------------

_Prompt*_:  When should you explicitly write `shouldComponentUpdate()`?

_Choices:*_

1. Always, if you call `setState()` and need that to reflect on the rendered UI.
2. Always, if you pass in new props and need that to reflect on the rendered UI.
3. Only if you are working with a large app with many dynamic components and need to optimize performance. *
4. Always, no matter the size of your app, if you want a high-performing app.

_Explanation*_:  React is quite fast by itself. You don't usually need to concern yourself with these methods unless you are working with a large app with many dynamic components.

----------------------------------

_Prompt*_:  When do you use a functional component?

_Choices:*_

1. If your component is stateful
2. If you're calling lifecycle methods
3. If you need a reference to the DOM element rendered by the component
4. If none of the above apply. *

_Explanation*_:  Right, these scenarios are all situations where you should declare your component as a class - a functional component can have logic in it, but it only takes the `props` object as its argument and returns JSX.
