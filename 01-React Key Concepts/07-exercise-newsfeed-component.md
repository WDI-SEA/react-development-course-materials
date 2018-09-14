# Exercise: Creating A Newsfeed Component

## Instructions

**Estimated Time:** 45min

1. In the HTML look for a section element with an id of main.  Nested within you will find  
   3 articles.
2. Using the sources array, defined below, create an App component that will recreate the section elements
-   - (45min / 3:15)

This exercise is meant to provide additional practice creating reusable React Components.

In the [Creating A Newsfeed Component](https://codepen.io/jkeohan/pen/PBvxvY?editors=0010) CodePen you will find 3 article elements within the HTML section generating the newsfeed articles visible on the page.

Perform the following to complete the lab: 

- Create an array called `newsFeedData` that will contain 3 objects with the following properties:  `title`, `tags`, `image`, and `impressions`
- Populate those objects based on those values assigned in the HTML.
- Create a `NewsFeed` component and pass it the `newsFeedData` array as `props`.
- The `NewsFeed` component will then render 3 `articles` based on properties of the objects in the `newsFeedData` array.

