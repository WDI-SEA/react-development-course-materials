# ![GA Cog Logo](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) State Recap

## Learning Objectives

*After this code-along section, you will be able to:*

* Describe the flow of methods in a component
* Identify the triggers for re-rendering of a component

---

## Review

```js
class Post extends Component {

  state = {
    body: "Check out this body property!"
  }

  changeBody = () => {
    let newBody = prompt("What should the new body be?")
    this.setState({
      body: newBody
    })
  }

  render() {
    return (
      <div>
        <h1>{this.props.title}</h1>
        <Author authorList={this.props.allAuthors} />
        <div>
          <p>{this.state.body}</p>
          <button onClick={this.changeBody}>Edit Body</button>
        </div>
        <h3>Comments:</h3>
        <Comment body={this.props.comments} />
      </div>
    )
  }
}
```

<aside class="notes">

**Talking Points**:

- Now that you've wrapped up the Blog project, take a moment to review the component lifecycle at a high level.

- Seen here is an example of a Post Component.

- In the `Post` component above, there are three things to notice:

* `state = {}`
* `changeBody()`
* `render()`

- Upon instantiation of your component, the initial state is set. Here we define that our component's state contains a `body` attribute whose value will start as the string we define.

</aside>

---

Let's consider a data flow example.

1. Here's the code that kicks everything off:

  ```js
  <Post />
  ```

2. Inside of this post component, state object is created:

```js
class Post extends Component {
  state = {
    body: "This is my first blog post"
  }
}
```

3. Next, we define a listener in the JSX `<button>` element. This calls the `changeBody()` method `.onClick`. That is defined here:

```js
  <button onClick={this.changeBody}>
    Edit Body
  </button>
```

4. When the _button_ is _clicked_, the `changeBody()` method is called.

  ```js
  changeBody = () => {
    let newBody = prompt("What should the new body be?")
    this.setState({
      body: newBody
    })
  }
  ```

<aside class="notes">

**Talking Points**:

- This method uses `prompt` to get a new value from the user (but please do not ever use `prompt` in production - users hate popups!).

- Then, `setState()` is called to update the component's state.  This will eventually lead to `render` being called to automatically re-render the component with the new data.

- Understanding the component lifecycle is key to being a productive React developer (and it will save you headaches).

</aside>

---

#### Check Yourself

When you `setState()`, what methods are fired? How are your `props` and `state` handled in the component? 

<aside class="notes">

**Talking Points**:

- Draw this out or comment throughout your code.

</aside>