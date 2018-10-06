# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  Exercise: Creating a Newsfeed Component

This exercise is meant to provide students with additional practice creating reusable React components.

## Instructions

**Estimated Time:** 45 min

1. In the HTML, look for a section element with an ID of `main`. Nested within it, you will find three articles.
2. Using the sources array (defined below), create an app component that will recreate the section elements.

In the [Creating a Newsfeed Component](https://codepen.io/jkeohan/pen/PBvxvY?editors=0010) CodePen, you will find three article elements within the HTML section generating the newsfeed articles visible on the page.

Perform the following to complete the lab: 

- Create an array called `newsFeedData` that will contain three objects with the following properties: `title`, `tags`, `image`, and `impressions`.
- Populate those objects based on those values assigned in the HTML.
- Create a `NewsFeed` component and pass it the `newsFeedData` array as `props`.
- The `NewsFeed` component will then render three `articles` based on properties of the objects in the `newsFeedData` array.

