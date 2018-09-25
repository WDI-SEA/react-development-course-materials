# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) React Router: Section Recap and Exercise


## Recap
What have we learned so far?
* Single Page Applications have specific URLs that are routed to display
  different content.
* React Router is a third-party library that we can install and use with React.
* Since React Router isn't built in to React, we must import its components.
* React Router makes it easy for us to route URLs to components.
* React Router automatically manipulates modern browser history mechanics.

Now let's put that to the test!

---

## Try It: Implement Router


Task:

- Create two new pages to your blog:
  1) An "About" page 
  2) A "Tiny T's Two Cents' Worth" page 
  - These pages don't need to have much content — just the header at the top saying what the page is and a paragraph description of your choosing.
  
- Create a navigation menu of list items that route to each page.
 

<aside class="notes">

**Talking Points**:


</aside>

---

Task:

- Create a navigation menu of list items that Route to each page.
  - These pages don't need to have much content — just the header at the top saying what the page is and a paragraph description of your choosing.
  
  
  <aside class="notes">

**Talking Points**:

- Each page is a component - we're learning to use React Router here!
  
_Fun Note:_ There's no reason you can't change the CSS, if you'd like! The CSS file that you'll change is `App.css`. If you'd like, you can grab ours [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/blob/master/projects/project-04-router/solution-code/src/App.css).
 - Thought exercise: Why is that the only CSS file you need to change?

**Hint**: You'll need multiple `.js` files

**Hint**: Do you have `react-router-dom` installed for this project?

**Hint**: You can instantiate a component with `props` inside of a `<Route>` element. An example is below:

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

---

## Solution


![Solution for Project](assets/router-solution.png)

<aside class="notes">

**Talking Point**:

Your solution should look something like what is seen here.

</aside>

