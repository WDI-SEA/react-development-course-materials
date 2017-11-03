### This is Quiz 4. It comes after the React Router exercise.
- It covers React Router, single page applications, and browser history mechanics.

**Notes**:
- [The link to quiz 4 is here](https://ga-instruction-sandbox.herokuapp.com/?lessonURL=https://ga-instruction.s3.amazonaws.com/json/REACT/unit-4/unit4-quiz.json). This is the link you give to students.

- At the end of the quiz, you can share [this review guide](../../../../react-review-guides/blob/master/unit-4-react-review-guide.md).

### Questions:
- Answers with an asterisk are correct.


_Prompt*_: Can you create a single page application in React without using React Router?


_Choices:*_

1. Yes *
2. No


_Explanation*_:  React Router is a third party library which handles the browser history mechanics for you, greatly simplifying your life, but you don't need to use it if you program all of that yourself. That said, just about everyone uses it!

----------------------------------

_Prompt*_: Which React component creates a nav bar?

_Choices:*_

1. Component
2. Link *
3. Route
4. Exact


_Explanation*_: `<Link>` creates `<a>` tags for you, navigating to the path you specify.

-----------------------------------

_Prompt*_: What does the `exact` keyword in React Router do?

_Choices:*_

1. All routes need this to define which component to render
2. It renders the new component with the exact state of the previous one
3. The nav bar will not work without it - it defines the set routes
4. The component associated with the route will only be shown if users are at exactly that URL path *


_Explanation*_: `<Link>` creates `<a>` tags for you, navigating to the path you specify.


-----------------------------------

_Prompt*_:  What's wrong with this code? Choose all that apply.

```js
class App extends Component {
  render() {
    return (
        <div>
          <Route path="/" component={Panda} />
          <Route path="/crocodile" component={Crocodile} />
          <Route path="/kangaroo" component={Kangaroo} />
        </div>
    )
  }
}
```


_Correct Response*_: Right! We need `exact` to make sure multiple components don't display at once, and the `<div>` needs to be wrapped by a `<Router>` component - so it'd be `return ( <Router> <div> ....`

_Incorrect Response*_: We need `exact` to make sure multiple components don't display at once, and the `<div>` needs to be wrapped by a `<Router>` component - so it'd be `return ( <Router> <div> ....`


_Choices:*_

1. The root path needs the `exact` keyword. *
2. The `<Route>` components need to be wrapped by a `<Router>` component inside of the `<div>`
3. The `<div>` needs to be wrapped by a `<Router>` component *
4. The declaration is correct.


----------------------------------

What's wrong with this code? Choose all that apply.

```html
  <Link nav to="/">Slash!</Link>{' '}
  <Link nav to="/crocodile">Crocodile!</Link>{' '}
  <Link nav to="/kangaroo">Kangaroo!</Link>
```


_Correct Response*_: Right! The `nav` keyword doesn't belong here - the `<Link>`s would instead be wrapped by a `<nav>` element.

_Incorrect Response*_: Not quite. The `nav` keyword doesn't belong here - the `<Link>`s would instead be wrapped by a `<nav>` element.


_Choices:*_

1. The root path needs the `exact` keyword.
2. The `nav` keyword doesn't belong here - the `<Link>`s would instead be wrapped by a `<nav>` element. *
3. The value of each `to` attribute needs to be the component.
4. The declaration is correct.


-----------------------------------

_Prompt*_: Where do the `<Link>` components go in a file?

_Choices:*_

1. Above the component class declaration
2. Inside the component class declaration, above the `render()` method
3. Inside the component class `render` method, above the `return()` method
4. Inside the component class declaration, inside the `<Router>` component *

_Explanation*_: The `<Link>` components are part of `<Router>` and rendered on the screen, and therefore they go inside the component class declaration, inside the `<Router>` component.

----------------------------------

_Prompt*_: Is this how you can pass props to a component within `<Route>`?

```html
<Route path="/games" component={
    () => (<Game title={title}
              publisher={publisher} />
)}/>
```

_Choices:*_

1. Yes *
2. No, you cannot pass props to a component within `<Route>`
3. No, you cannot use arrow functions within `<Route>`
4. No, there are not angle brackets around the component within `<Route>`

_Explanation*_:  This code is correct!

-----------------------------------

_Prompt*_: If you're going to put your website online and not keep it locally, you still need to import `BrowserRouter` and `Route`, but you don't need to install Router.



_Choices:*_

1. True
2. False *


_Explanation*_:  False! Because React Router is a third-party library, we'll need to download React Router and save it to our `package.json` file as a dependency.


----------------------------------

_Prompt*_: As long as you have your `<Link>` components written correctly, you can have either the below code **or** `<Route>` declarations - you don't need both for the nav bar to work.

```html
<div>
  <Component1></Component1>
  <Component2></Component2>
  <Component3></Component3>
</div>
```

_Choices:*_

1. True
2. False *

_Explanation*_: False! The `<Link>` component only takes a path, so you need `<Route>` elements to connect the paths to components.

----------------------------------

_Prompt*_: What defines a single page application? Choose all that apply.


_Correct Response*_: Right! Many frameworks enable you to write single page applications! These are websites that serve only one web page and then change the content of that page dynamically, without refreshing or sending the user to a separate page.

_Incorrect Response*_: Many frameworks enable you to write single page applications! These are websites that serve only one web page and then change the content of that page dynamically, without refreshing or sending the user to a separate page.


_Choices:*_

1. Only applications using React can be single page applications.
2. If content dynamically changes on the page without a page reload. *
3. If a user can click for new content and is not sent to a new page. *
4. If historical modern browser mechanics work.
