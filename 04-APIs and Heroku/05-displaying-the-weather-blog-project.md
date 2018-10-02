# ![GA Cog Logo](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Blog Project: Displaying the Weather

## Implement the `fetch` API

 ![logo](assets/open-weather-map-logo.png)

**Resources**:

- OpenWeather API: http://openweathermap.org/current

- OpenWeather API documentation: http://openweathermap.org/current

- Info on `fetch`: https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch

<aside class="notes">

**Talking points**:

- Time to show off! You're going to display the weather on your "Dinosaurs are awesome" blog (because reptiles are rather finicky about the weather).

- You'll use the OpenWeather API to fetch weather information from a certain zip code and update your blog to display the current weather.

- Here's the documentation for the OpenWeather API.

- If you'd like, you can read about `fetch` on MDN.

</aside>

---

![Solution for Project](assets/dino-blog-weather.png)

<aside class="notes">

**Talking point**:

- At the end of this exercise, your solution will look like what's seen here.

</aside>

---

### Requirements

On your "About" page, ask the user to input a zip code.

- You can learn more about forms [here](https://facebook.github.io/react/docs/forms.html).
  - When this event fires, take the `event.target.value` and `fetch()` from the OpenWeather API.

- Use the response from the API to display the current temperature, the high and low temperatures, the current weather description, and the name of the city.
  - Note: Our solution uses Fahrenheit. You're free to use Celsius if you'd like.

**Important notes**:

- Because the OpenWeather API is not an open API, every request must end with this API key:  `&appid=052f26926ae9784c2d677ca7bc5dec98`.

- As an example, this is a URL you might send a `fetch()` request to: `http://api.openweathermap.org/data/2.5/weather?zip=60614,us&appid=052f26926ae9784c2d677ca7bc5dec98`.

<details>
  <summary>Skeleton Code</summary>

  ```js
import React, { Component } from 'react';

class About extends Component {

  this.state = {
     // your required states here
  }

  handleChange = (event) => {
    this.setState({zipcode: event.target.value})
    console.log('Your zip code is' + this.state.zipcode)
  }

  handleSubmit = (event) => {
    // your fetch here
    // your state updates go under function(json)
  }

  render() {
    return (
      <div>
        <form onSubmit={this.handleSubmit}>
        <p>
          // display weather information here
        </p>
        <label>
          Please enter your zip code for the weather:
          <input type="text" onChange={this.handleChange} />
        </label>
        <input type="submit" value="Get my forecast!" />
      </form>
      </div>
    )
  }
}


export default About

```

</details>

<aside class="notes">

**Talking points**:

- **Hint 1:** You'll only need to re-work the `About` component. Nothing else needs to change.

- **Hint 2:** To see how to handle the form, check out the skeleton code.

</aside>

---

### Optional


<aside class="notes">

![alt](assets/weather.png)


**Talking point**:

- Spend a little time styling the page. Here's some inspiration (don't worry about the lens flare).
