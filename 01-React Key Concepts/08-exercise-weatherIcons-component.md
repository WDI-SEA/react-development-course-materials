# Exercise: Creating A WeatherIcon Component

## Instructions

**Estimated Time:** 30min

This exercise is meant to provide additional practice creating reusable React Components.

In the [Creating A WeatherIcons Component](https://codepen.io/jkeohan/pen/NLdOwb?editors=0010) CodePen you will find five weather elements that are being generated within the HTML section. 

Perform the following to complete the exercise: 

- Create an array called `weatherData` that will contain five objects with the following properties:  `img`, `conditions` and `time`.
- Populate those objects based on those values assigned in the HTML.
- Create a `WeatherIcons`  component and pass it the `weatherData` array as `props`.
- The `WeatherIcons` component will then render five `weather` divs based on properties of the objects in the `weatherData` array.
