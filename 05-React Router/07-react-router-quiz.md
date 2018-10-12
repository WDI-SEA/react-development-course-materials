# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Quiz: React Router

**Notes**:
- The link to the React Router quiz is [here](https://ga-instruction-sandbox.herokuapp.com/?lessonURL=https://ga-instruction.s3.amazonaws.com/json/REACT/unit-4/unit4-quiz.json). Give students this link.

- Approximate time to complete quiz: 20 minutes

- Approximate time to discuss or review quiz: 20 minutes

- At the end of the quiz, you can share [this review guide](https://git.generalassemb.ly/react-development/react-development-course-materials/blob/master/Additional%20Resources/Review%20Guides/react-key-concepts-review-guide.md). It's also linked for students on the myGA platform at the end of quiz.

## Questions

- Answers with asterisks are correct.

**Prompt**: Can you create a single-page application in React without using React Router?

**Choices**:

1. Yes *
2. No


**Explanation**: React Router is a third-party library that handles the browser history mechanics for you. You don't need to use it if you program all of that yourself, but just about everyone does.

----------------------------------

**Prompt**: Which React component creates a nav bar?

**Choices**:

1. Component
2. Link *
3. Route
4. Exact


**Explanation**: `<Link>` creates `<a>` tags for you, navigating to the path you specify.

-----------------------------------

**Prompt**: What does the `exact` keyword in React Router do?

**Choices**:

1. All routes need this to define which component to render.
2. It renders the new component with the exact state of the previous one.
3. The nav bar won't work without it — it defines the set of routes.
4. The component associated with the route will only be shown if users are at exactly that URL path. *

**Explanation**: With the `exact` keyword, the component associated with the route will only be shown if users are at exactly that URL path.


-----------------------------------

**Prompt**: What's wrong with the following code? Select all that apply.

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

**Choices**:

1. The root path needs the `exact` keyword. *
2. The `<Route>` components need to be wrapped by a `<Router>` component inside the `<div>`.
3. The `<div>` needs to be wrapped by a `<Router>` component. *
4. The declaration is correct.

**Explanation**: We need `exact` to make sure multiple components don't display at once. The `<div>` also needs to be wrapped by a `<Router>` component, so it would be `return ( <Router> <div> ....`.

----------------------------------

**Prompt**: What's wrong with this code? Select all that apply.

```html
  <Link nav to="/">Slash!</Link>{' '}
  <Link nav to="/crocodile">Crocodile!</Link>{' '}
  <Link nav to="/kangaroo">Kangaroo!</Link>
```


**Choices**:

1. The root path needs the `exact` keyword.
2. The `nav` keyword doesn't belong here. The `<Link>` components would instead be wrapped by a `<nav>` element. *
3. The value of each `to` attribute needs to be the component.
4. The declaration is correct.

**Explanation**: The `nav` keyword doesn't belong here. The `<Link>` components would instead be wrapped by a `<nav>` element.

-----------------------------------

**Prompt**: Where do the `<Link>` components go in a file?

**Choices**:

1. Above the component class declaration.
2. Inside the component class declaration, above the `render()` method.
3. Inside the component class `render()` method, above the `return()` method.
4. Inside the component class declaration, inside the `<Router>` component. *

**Explanation**: The `<Link>` components are part of `<Router>` and rendered on the screen. Therefore, they go in the component class declaration, inside the `<Router>` component.

----------------------------------

**Prompt**: Is this how you pass props to a component within `<Route>`?

```html
<Route path="/games" component={
    () => (<Game title={title}
              publisher={publisher} />
)}/>
```

**Choices**:

1. Yes. *
2. No, you can't pass props to a component within `<Route>`.
3. No, you can't use arrow functions within `<Route>`.
4. No, there are no angle brackets around the component within `<Route>`.

**Explanation**: This code is correct.

-----------------------------------

**Prompt**: True or false: If you put your website online and don't keep it locally, you still need to import `BrowserRouter` and `Route`, but you don't need to install React Router.



**Choices**:

1. True
2. False *


**Explanation**: Because React Router is a third-party library, we'll need to download it and save it to our `package.json` file as a dependency.


----------------------------------

**Prompt**: True or false: As long as you have your `<Link>` components written correctly, you can have the code below **or** `<Route>` declarations. You don't need both for the nav bar to work.

```html
<div>
  <Component1></Component1>
  <Component2></Component2>
  <Component3></Component3>
</div>
```

**Choices**:

1. True
2. False *

**Explanation**: The `<Link>` component only takes a path, so you need `<Route>` elements to connect these paths to components.

----------------------------------

**Prompt**: What defines a single-page application? Select all that apply.


**Choices**:

1. Only applications using React can be single-page applications.
2. If content dynamically changes on the page without a page reload. *
3. If a user can click on new content and isn't sent to a new page. *
4. If historical modern browser mechanics work.

**Explanation**: Many frameworks enable you to write single-page applications. These are websites that serve only one webpage and change the content of that page dynamically, without refreshing or sending the user to a separate page.
