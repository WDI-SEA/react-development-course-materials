# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) React Router: Section Recap and Exercise


## Recap
What have we learned so far?
* Single-page applications have specific URLs that are routed to display different content.
* React Router is a third-party library that we can install and use with React.
* Since React Router isn't built into React, we must import its components.
* React Router makes it easy to route URLs to components.
* React Router automatically manipulates modern browser history mechanics.

Now let's put that to the test.

---

## Try It: Implement Router on Your Dinosaur Blog


Task:

- Create two new pages on your blog:
  - An "About" page (bios of the dino authors).
  - A "Tiny T's Two Cents' Worth" page (Tiny's opinions on the saurian political scene).
 
- Get creative and add some fun additional content to these other routes.
  
- Create a navigation menu that routes to each page.
 
 
<aside class="notes">

**Talking point**:

- Each page is a component. We're learning to use React Router here.
  
**Teaching tips**:

- This exercise requires students to refactor their `App.js` file.

  - **Hint**: You'll need multiple `.js` files.

  - **Hint**: Do you have `react-router-dom` installed for this project?

  - **Hint**: You can instantiate a component with `props` inside a `<Route>` element. 

</aside>

---

```js
<Route path="/blog" component={
    () => (<Blog title={post.title}
              author={post.author}
              body={post.body}
              comments={post.comments} />
)}/>
```

**But, wait! This is not the best choice.**

<aside class="notes">

**Talking points**:
- The above will work, but it's not a great solution and can create performance issues. The [official React documentation]( https://reacttraining.com/react-router/web/api/Route/component) states: "When you use `component` the router uses `React.createElement` to create a new React element from the given component. That means if you provide an inline function to the `component` prop, you would create a new component every render. This results in the existing component unmounting and the new component mounting instead of just updating the existing component. When using an inline function for inline rendering, use the `render` or the `children` prop."

- So if you’re not supposed to pass a function to `component`, what’s the solution? Turns out the React Router team predicted this problem and gave us a handy solution. Instead of using `component`, use the `render` prop. `render` accepts a functional component and that function won’t unnecessarily get remounted like `component`. (Source: [Tyler Mcginnis](https://tylermcginnis.com/react-router-pass-props-to-components/))

</aside>

---

```js
<Route path="/blog" render={
    () => (<Blog title={post.title}
              author={post.author}
              body={post.body}
              comments={post.comments} />
)}/>
```

Much better!

<aside class="notes">

**Talking point**:

- Here's the `render` prop. Note that the function will receive the same props that `component` would receive. So you can take those and pass them along to the `render` prop.

</aside>

---

## Solution


![Solution for Project](assets/implement-router-solution.png)

<aside class="notes">

**Talking point**:

* Your solution should look like what's seen here.

</aside>

