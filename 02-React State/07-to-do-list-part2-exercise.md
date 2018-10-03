# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Exercise: To-Do List, Part 2

To-dos change. So should our list.

<aside class="notes">

**Talking Points**:

- Now we have a to-do list! But it isn't changeable, and we can't just _think about_ eating ice cream and going to the gym forever. At some point, we have to actually eat the ice cream (deleting it from the list) and find a gym buddy (adding that to the list). In other words, we need to be able to change the list!

</aside>

---

## Let the Refactoring Begin!

<aside class="notes">

**Talking Points**:

- Remember, in a React component, `state` is just another object, like `props`. The biggest difference is that `state` can be changed (remember, though, to always change it through the method `setState`). The exception is setting the initial state, which is only done once: when initializing a React component. In order to pass items to the `ToDoList` component and make them mutable, we'll need to set the state of our `MyList`. 

- This is going to require a lot of refactoring! We're going to be swapping out places where we started using props, and replacing it with our changable state.

</aside>

---

## Clearing the items

* At the top of the `MyList` component, create an initial state object with an attribute called `toDoItemArray`. It should be equal to the initial list that's passed in.
* Don't forget to change the `map` call!
* Always check to be sure your website is accurate (it should still look the same).
* Make a small change, and then test to see if it works. Don't change too many things at once!




**Talking Points**:

- We're going to add a button to the list that allows users to clear away
everything in it. First, let's make sure the list is all set up to display
items properly already. The steps here walk you through that.

- Next, we'll look into making this list changeable. Remember, updating state will involve calling `setState`. Let's use a simple example with a "clear" button in `MyList`.

</aside>

---

## Clearing the Items

First, in `MyList`, we define the function that will be called by the button:

```js
clearList = (e) => {
  this.setState({
    toDoItemArray: []
  })
}
```

Then, add a button after the whole `<ul>` list.

**MyList.js**
```html
<ul>
  ...
</ul>
<button onClick={this.clearList}>Finished the list!</button>
```

This makes our `MyList` component look like this:

**MyList.js**

```js
class MyList extends Component {

  state = {
      toDoItemArray: ["Buy ice cream", "Eat ice cream", "Go to the gym"]
  }
  
  clearList = () => {
    this.setState({
      toDoItemArray: []
    })
  }

  render() {

    let todoItems = this.state.toDoItemArray.map( (item, index) => (
      <ListItem doThis={item} key={index} />
    ))

    return (
      <div>
        <h1>Things I should stop procrastinating:</h1>
        <ul>
          {todoItems}
        </ul>
        <button onClick={this.clearList}>Finished the list!</button>
      </div>
    )
  }
}

export default MyList
```

<aside class="notes">

**Talking Points**:

- Don't forget to try it out!

</aside>

---

### Now what will happen when we click on the button?


<aside class="notes">

**Talking Points**:

- Now when we click on the button, the following will occur:
* `this.setState` will set the state, `toDoItemArray`, to be empty: `{toDoItemArray: []}`
* The render function for `MyList` will be called and re-render the component.
* We'll feel good about ourselves for going to the gym, even if we ate ice cream first.


</aside>

---

### Sure-fire Coding

 ```js
 clearList = () => {
   console.log("Clearing list!")
   this.setState({
     toDoItemArray: []
   })
 }
 ```

 > Another great way to debug this feature is to use the React Dev Tools.  Select the React tab and click on the `MyList` component, now you can utilize `$r.clearList()` in the JS console to directly call the method.

<aside class="notes">

**Talking Points**:

- There are lots of things that can go wrong when we try to hook up new functionality to our app. Our button might be set up wrong, it might not call the correct function, the function may have an error in it.

 - Let's add a `console.log()` statement on the first line in our `clearList` function. This is an excellent debugging practice. Adding `console.log()` proves to us that the function is actually executing. This proves to us that there's
nothing wrong with how we hooked up the button and helps narrow our focus in case something else went wrong.

 Let's say you click the button and the list isn't cleared.
 * If you didn't see `"Clearing list!"` in the console then you know something is
   wrong with the way you hooked up the button. Investigate that.
 * If you did see `"Clearing List!"` in the console and the list still didn't
   clear then you know you need to investigate your code inside the function
   after the click.

 Adding simple sanity checks like this to your code will make you a productive
 programmer.

</aside>

---

## Adding items

* Create an attribute `newItem` in the state to hold the new item that the user inputs.

<aside class="notes">

**Talking Points**:

- Let's add one more thing to our app: an input field for more items. In order to do so, we'll need a variable to represent the new item we'll be entering.

- Make a new state attribute, initializing `newItem` to a blank string. (Hint: remember, `state` is just a JavaScript object, so you need a comma between key-value pairs.)

---

## Adding items (continued)

* `handleChange`, for when we type characters into an input field and change the value of `newItem`  
 * We'll need to get the current value of the input field and set state accordingly.
 > Create this function with an event parameter. Inside the function, change the state of `newItem` to `e.target.value` - this will be the value the user entered into the form.

* `addItem`, for when we submit the form
  * We'll need to make a copy of `toDoItemArray`, push the `newItem`, set `state` and finally clear `newItem`.
  
 > Create this function with an event parameter of 'e'. Inside the function, create a new variable initialized to the value of the array that is saved in state. Then, use `yourArray.push(<value>)` to push the new item from the state into the array. Set the `newItem` state back to an empty string, and set the `toDoItemArray` state to your new array.

<aside class="notes">

**Talking Points**:

- We'll also need these two additional functions to represent the following changes in state.

</aside>

---

## Adding items (continued)

```js
<form>
  <input type="text"
   placeholder="Type an item here"
   onChange={this.handleChange}
   value={this.state.newItem}
  />
  <button onClick={this.addItem}>Add it!</button>
</form>
```

<aside class="notes">

**Talking Points**:

- Lastly, we'll need to add a form to our `render` method.

- Note we can use `onChange` on the `input` field to trigger an event when the text in the box is changed.  

- Note any function called when an event occurs (like functions that happen `onClick`, `onSubmit`, or `onChange`) can accept an argument that is the event. We pass this in as `e` to `newItemChange` and `addItem`.

**Teaching Tip**:

- Set the value of the `input` to `this.state.newItem` before adding `handleChange`. This is an opportunity to show why we need an onChange event.

</aside>

---

## Debugging Adding Items

```js
addItem(event) {
  // prevent the event from running the default "submit" event.
  event.preventDefault()

  // then the rest of your code.
  // ...
}
```
<aside class="notes">

**Talking Points**:

- If you click "Add it!" and the page doesn't change, and you think you've done
everything right there's one thing you're probably missing. Here's a good
debugging strategy to figure out what's wrong.

- Add a `console.log` statement inside your `addItem` function to make sure the
function is actually being executed. If you don't see simple output in your
console then there's something wrong with how you hooked up the button to the
`addItem` function. You need to investigate how the button is attached to the
function.

- If you click the button and an empty item appears in your list then you need
to investigate how you're retrieving the text value out of the form input.
Use a console statement to print the value of the text to make sure you're
accessing it correctly.

- If you see a simple console statement working, and you see the correct text
being printed and you still don't see items added to the list correctly then
there's one last hiccup that causes lots of problems: the button is inside a
form and it triggers a `submit` event. Submit events make the page reload, or
(more accurately) navigate to the url `action` attribute of the form. If there's
no `action` attribute defined the page just navigates to itself, and reloads.

- Make sure your `addItem` function accepts an `e` event parameter and calls
.preventDefault to stop the submit event from firing.

</aside>

---

### What next?

Can you figure out how to implement some other new features?

<aside class="notes">

**Talking Points**:
- We now have an interactive to-do list!  We can add and remove items from our list.  This is just the beginning though.  There are all sorts of other features you can add.  Can you figure out how to implement some other new features?
- Here are some ideas for you to implement:
1. Remove one item instead of clearing everything
2. Add a date to each todo item, and build functionality to arrange items from newest to oldest and vice versa
3. Utilize `localStorage` to save your items to the browser so it will persist on refresh.

</aside>
