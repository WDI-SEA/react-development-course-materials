## ![](https://s3.amazonaws.com/python-ga/images/GA_Cog_Medium_White_RGB.png) {.separator}
<h1>Introduction to Redux</h1>

---

## Learning Objectives

*After this lesson, you will be able to:*

* Define what Redux is and why you would use it
* Explain what actions, reducers and the Redux store is.
* Name benefits of using Redux.

---

## Redux

![logo](assets/redux-logo.png)


<aside class="notes">

**Talking Points**:



**Teaching Tips**:

* Give real life examples of why you might use Redux. If you've used Redux in the past, reference your projects.

</aside>

---

## Redux is:

Redux is a lightweight state management tool.

<aside class="notes">

**Talking Points**:


</aside>

---

## Why use Redux?

As we've learned, React is pretty good at state management without any additional tools. So why Redux too?

*  As your application becomes larger, it becomes increasingly difficult and confusing to manage state across multiple shared components.
*  Keep in mind, components are reusable so you might be using these components across several pages or screens within your app.

Imagine multiple components, that all need to talk to each other, but for different reasons. You might have a hard time understanding where state should live. In a perfect world, component data should be isolated to that particular component. Now consider sibling components (insert an example) and how you would share that data.

As you've learned so far, to share data among siblings, a state has to live in the parent component. The method for updating this state is provided by this parent component and passed as props to these sibling components.

<aside class="notes">

**Talking Points**:

* Use specific instances where you have components used in several places. Like, an input box that you might use for a contact page, submission form, sign up email, etc.

</aside>

---

## How it Works

Though it's tricky to grasp at first, Redux is actually pretty simple.

_One central store holds the entire state of the application._ Every component can access state without passing down props from one component to another.

# How you ask?!

* **Actions:** Actions are _events_. They are the only way you can send information from your app to your Redux Store. This data can sent is typically based on UI events, API calls, and/or event handlers.

* **Reducers:** Reducers are _pure functions_ that take the current state of an app, complete an action and then return a new state.

* **Store:** The store simply _stores the application state_.

<aside class="notes">

**Talking Points**:


</aside>

---

## Redux Benefits

* **Redux provides predictable state**

* **Helps keep code clean and maintainable**

* **Provides easy troubleshooting and debugging**

* **It's easy to test!**

<aside class="notes">

**Talking Points**:


</aside>

---


## Redux Alternatives

<aside class="notes">

**Talking Points**:


</aside>

---
