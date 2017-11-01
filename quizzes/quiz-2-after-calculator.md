### This is Quiz 2. It comes after the Calculator exercise.
- It covers state, `constructor()`, and `map`.

**Notes**:
- [The link to quiz 2 is here](https://ga-instruction-sandbox.herokuapp.com/?lessonURL=https://ga-instruction.s3.amazonaws.com/json/REACT/unit-2/unit2-quiz.json). This is the link you give to students.

- At the end of the quiz, there is a link to [this review guide](../../../../react-review-guides/blob/master/unit-2-react-review-guide.md). Students will see this in the quiz slides; you don't need to share the link.

### Questions:
- Answers with an asterisk are correct.

_Prompt*_: Where does `constructor()` go, and when do you need it?


_Choices:*_

1. At the top of the component class; you always need it for accurate setup of that class.
2. At the top of the component class; you only need it if you are changing any initial configurations for that class. *
3. In the component class' `render()` method; you always need it for accurate setup of that class.
4. In the component class' `render()` method;  you only need it if you are changing any initial configurations for that class.


_Explanation*_:  The constructor is only needed if you're changing initial setup - like setting a state. It is its own method and goes at the top of the component class, not inside the `render` method.

-----------------------------------

_Prompt*_: What happens when you call `setState()`?

_Choices:*_

1. The new state will be passed into the current state of the component. The virtual DOM tree is updated. A diff is run between the virtual DOM tree and the regular DOM tree. Only the correspondingly elements in the regular DOM tree will update. *
2. The virtual DOM tree is updated. A diff is run between the virtual DOM tree and the regular DOM tree. The new state will be passed into the current state of the component. Only the correspondingly elements in the regular DOM tree will update.
3. The virtual DOM tree is updated. The new state will be passed into the current state of the component. Only the correspondingly elements in the regular DOM tree will update.
4. The new state will be passed into the current state of the component. Only the correspondingly elements in the regular DOM tree will update.

_Explanation*_:  `setState()` first updates the state of the component; this causes the virtual DOM to be updated, which in turn triggers React to compare the virtual DOM and regular DOM. Only the changed elements will update.

-----------------------------------

_Prompt*_:  If we have the code below, inside of the Painting component, will `dinosaur` be treated as a prop or a state?

```html
<Painting dinosaur="velociraptor" />
```

_Choices:*_

1. prop *
2. state

_Explanation*_: Elements that are passed in to a component are treated as a prop within that component. For `dinosaur` to be considered a state within `Painting`, it would need to be a new element declared within `Painting`'s `constructor` - not passed in to `Painting`.

----------------------------------

_Prompt*_: What is wrong with the below code? Choose all that apply.

```js
class Compliment extends Component {
  constructor () {
    state = {
      compliment = "You're so awesome!"
    }
  }
}
```

_Correct Response*_:  Correct! State is set with `this.state`, and the name-value pair is separated with a colon, not an equals sign. Lastly, all constructors need to start with a call to `super()` to initialize the default class before modifying it.

_Incorrect Response*_: Not quite. State is set with `this.state`, and the name-value pair is separated with a colon, not an equals sign. Lastly, all constructors need to start with a call to `super()` to initialize the default class before modifying it.

_Choices:*_

1. You can't have a state with the same name as the component
2. State is set with `this.state`, not just `state` *
3. State is set with colons, not equal signs. It should be `compliment: "You're so awesome!"` *
4. Constructors need to begin with a call to `super()` *
5. All of the above.

----------------------------------

_Prompt*_: What is wrong with the below code? Choose all that apply.

```js
class Volcano extends Component {

  erupt() {
    setState({
      lava: flowing
    })
  }

  render() {
    return (
      <h3>Warning: Lava is currently {this.lava}</h3>
      <h3>Warning: Lava is currently {state.lava}</h3>
    )
  }
}

```

_Correct Response*_:  Correct! States need to be declared before they can be used, so there needs to be a constructor method initializing `lava`. Additionally, state is called with `this.state.Name` and setting state is done with `this.setState()`

_Incorrect Response*_:  Not quite. States need to be declared before they can be used, so there needs to be a constructor method initializing `lava`. Additionally, state is called with `this.state.Name` and setting state is done with `this.setState()`


_Choices:*_

1. State is modified with `this.setState()`, not just `setState()` *
2. The state `lava` was never initialized. *
3. State is called by JSX with `{this.state.lava}`, so both the `<h3>` statements need to change. *
4. State is called by JSX with `{this.lava}`, so the second `<h3>` statement needs to change.
5. State is called by JSX with `{state.lava}`, so the first `<h3>` statement needs to change.


-----------------------------------

_Prompt*_: Using React, if you refresh a webpage, you never lose information since everything is stored in the component or browser state.

_Choices:*_

1. True
2. False *

_Explanation*_: `state` just represents the state of data on our page. Something saved to `state` in React is not automatically saved to a database or to local storage. If you refresh the page, all `state` information is lost.

----------------------------------

_Prompt*_:  What is `map`?

_Choices:*_

1. A map is like a `while` loop. With `map`, you use an existing iterator to navigate through each item until you break the loop.
2. A map is like a `for` loop. With `map`, you use an existing iterator to navigate through each item in an array.
3. A map is like a `for` loop. With `map`, you make a new variable and with it iterate through each item in an array. *
4. A map is like a `while` loop. With `map`, you make a new variable and with it iterate through each item until you break the loop.

_Explanation*_:  Right! We use `map` to iterate over an array, like a `for` loop, and perform an action on each item, usually saving this into a new variable.

-----------------------------------

_Prompt*_:  Is the correct syntax for `map`?

```js
const drinks = ['tea', 'espresso', 'milkshake']

let myDrinks = drinks.map( (soda, index) => {
  return newDrink = 'I love' + soda
})
```

_Choices:*_

1. No - `soda` was never initialized
2. No - `index` is a keyword and cannot be used as a variable
3. No - the first line of the function should be `let myDrinks = map( (drinks, index)`
4. Yes *

_Explanation*_:  Yes! This is a perfectly valid way to use `map` to iterate an array, modify it, and save the modified array into a new variable.

----------------------------------

_Prompt*_:  Is the correct syntax for `map`, if the array is a prop named `Bear`?

```js

let Bears = this.prop.Bear.map( (bearType, index) => {
  return cuteBear = 'I love' + bearType
})
```

_Choices:*_

1. No - the array should be called with `this.props.Bear`, making it `this.props.Bear.map` *
2. No - the array should be called with `Bear`, making it simply `Bear.map`
3. No - `bearType` was never initialized
4. Yes

_Explanation*_:  It's not, because while all of the `map` specific syntax is correct, you would call the `prop` with `this.props.Bear` - with an s on `props`.

----------------------------------

_Prompt*_:  True or False: I can set state when calling the state's component. For example, let's say I have a file `Tropical.js` which contains a component `Tropical`, with the state `pineapple` initialized inside the `Tropical` component. Then, in a separate file, `Recipes.js`, I can have this code to change the state of `pineapple` to `delicious` inside of the `Tropical` component:

```js
ReactDOM.render(
  <Tropical pineapple="delicious" />,
  document.getElementById('root')
)
```

_Choices:*_

1. True
2. False *

_Explanation*_:  Right, this is false - if the state `pineapple` is initialized in `Tropical`'s constructor, then in `Recipes.js`, the state `pineapple` does not exist. Here, `pineapple` would be passed in as a prop which happens to have the same name as the state initialized in `Tropical.js`. They could each be accessed, respectively, by `this.state.pineapple` and `this.props.pineapple`
