# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Introduction to React Router


## Learning Objectives
After this lesson, you'll be able to:
* Describe React Router's main features: routing, components, history.
* Use React Router to map URLs to components.
* Use React Router to create links to different pages.

## React Router

![logo](assets/small-react-router-logo.png)


<aside class="notes">

**Talking points**:

* It's great that HTML5 introduced new browser history mechanics to make it easier for us as developers to build single-page applications. It's also good to know what's going on under the hood.

* However, we're actually not using these new features directly.

* Instead, we'll use a tool called **React Router**, which bundles everything together so we don't have to worry about it.



**Teaching tip**:
* Play the intro to React Router [video](https://generalassembly.wistia.com/medias/tep72w77ir).

</aside>

---

React Router is a third-party library that makes it easy for us to route URLs — not to different pages but by dynamically loading different components on the same page as the user navigates to different URLs.

React Router provides:

* **Routing:** easily define the content associated with a URL.
* **History:** automatically manage browser history when the user navigates between content.

<aside class="notes">

**Talking points**:

* React Router is actually a **third-party** library. This means it's not built by React and was written by another group of developers.
* Even though React Router is third-party software, it's extremely useful, trustworthy, and popular, so don't be afraid to use it. With more than 30,000 stars on GitHub, it’s safe to assume React Router is here to stay.
* Once we define how the URLs are routed to the components, React Router will manage our SPA's browser history automatically.

</aside>





