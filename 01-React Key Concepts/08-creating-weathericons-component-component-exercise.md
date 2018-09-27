# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  Exercise: Creating a WeatherIcons Component

## Instructions

**Estimated Time:** 30 min

This exercise is meant to provide students with additional practice creating reusable React components.

In the [Creating a WeatherIcons Component](https://codepen.io/jkeohan/pen/NLdOwb?editors=) CodePen, you will find five weather elements generated within the HTML section.

Perform the following to complete the exercise: 

- Create an array called `weatherData` that will contain five objects with the following properties: `img`, `conditions`, and `time`.
- Populate those objects based on those values assigned in the HTML.
- Create a `WeatherIcons` component and pass it the `weatherData` array as `props`.
- The `WeatherIcons` component will then render five `weather` `div`s based on properties of the objects in the `weatherData` array.
