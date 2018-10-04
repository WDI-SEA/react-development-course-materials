# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Quiz: APIs, Heroku, and Imperative and Declarative Programming #

**Notes**:
- The link to the APIs, Heroku, and imperative and declarative programming quiz is [here](https://ga-instruction-sandbox.herokuapp.com/?lessonURL=https://ga-instruction.s3.amazonaws.com/json/REACT/unit-5/U5L5.json). This is the link you give to students.

- Approximate time to complete quiz: 20 minutes

- Approximate time to discuss or review quiz: 20 minutes

- At the end of the quiz, you can share [this review guide](https://git.generalassemb.ly/react-development/react-development-course-materials/blob/master/Additional%20Resources/Review%20Guides/react-key-concepts-review-guide.md). It's also linked for students on the myGA platform at the end of the quiz.

## Questions
- Answers with an asterisk are correct.


**Prompt**:
You want to embed a Google Map into your website. What do you do?

**Choices**:
1. Host the page on Heroku and point Heroku to the API.
2. Make a `GET` request to the API and `render` the response in your component. *
3. Send a `fetch` to Heroku to host the API and `render` the response in your component.
4. Put the API URL into the `render` method of your component — APIs automatically render.

**Explanation**: Making a `GET` request in JavaScript is done with `fetch()`. You make a `GET` request to the API, which returns a map that you can render.

---
**Prompt**:
Where should this code go?

```js
let poemApi = 'http://api.open-notify.org/astros.json'
fetch(poemApi)
  .then((response) => {
    return response.json()
  }).then((json) => {
      base.setState({ shakeSpeare: json.poem })
  }).catch((ex) => {
    console.log('An error occured while parsing!', ex)
  })
}
```

**Choices**:
1. `constructor()`
2. `componentDidMount()` *
3. `componentDidLoad()`
4. `componentWillMount()`

**Explanation**: If you need to load data from a remote endpoint, `componentDidMount()` is where you instantiate the network request.

---
**Prompt**:
Which of the following will likely be returned to your application when you call an API? Choose all that apply.

**Choices**:
1. JSON *
2. JSX
3. XML *
4. JavaScript

**Explanation**: JSON and XML are two major serialized data formats you will typically encounter when getting information over HTTP.

---
**Prompt**:
When writing a program, Sanju writes out every step in pseudocode, then codes each line. For example:

```js
// ask everyone in the room to line up
let room = ['Miguel', 'Katie', 'Susana', 'Shakira']
// for every person in the line
for (let i = 0; i < room.length; i++) {
// ask each person to come to the front of the room
  let person = room[i]
  //  ask each person to speak their name
  console.log("Imperative way: " + person) }
```

Is this imperative or declarative programming?

**Choices**:
1. Imperative *
2. Declarative

**Explanation**: It's imperative. Imperative is the approach to programming where you write every single thing that happens.

---
**Prompt**: Does React.js generally use an imperative or declarative approach to programming?

**Choices**:
1. Imperative
2. Declarative *

**Explanation**: React.js is a framework that focuses on simplicity and readability; it uses a declarative approach.

---
**Prompt**: What is Heroku?

**Choices**:
1. A cloud platform that allows developers to quickly deploy applications to the internet. *
2. A cloud platform that you can bootstrap your application to which enables easy routing of URLs.
3. A service that provides raw data for public use — usually in JSON or XML.
4. A service that provides raw data for your application to deploy to the internet.

**Explanation**: Heroku is a cloud platform that allows developers to quickly deploy applications to the internet. It's free for your first five apps.

---
**Prompt**: Ari is trying to call an API, but his program is throwing an error. He's sure that the API URL is correct, he defined the state, and he put the code in the correct place in his program. Looking at his code, what might be a reason that the API call isn't working? Choose all that apply.

```js
// fetch an album
let spotifyAPI = 'https://api.spotify.com/v1/albums/4aawyAB9vmqN3uQ7FjRGTy'
fetch(spotifyAPI)
  .then((response) => {
    return response.json()
  }).then((json) => {
      base.setState({ music: json.album })
  }).catch((ex) => {
    console.log('An error occured while parsing!', ex)
  })
}
```

**Choices**:
1. The API is private and requires an API key. *
2. `album` is not one of the pieces of information returned by the Spotify API. *
3. Ari's code is off — the `catch` statement is always being called because there's no explicitly defined `if` keyword.
4. Ari's code is off — `fetch` is its own function and therefore everything after `fetch(spotifyAPI)` should be encased in curly braces.

**Explanation**: If an API call isn't working and you're sure your code is correct, the first thing to check is the documentation of the API. Make sure the API isn't private and is returning the parameters you think it's returning (like `album`).

---
**Prompt**:

Is this valid JSON?

```html
<users>
  <user id="0">
    <name>Superman</name>
  </user>
  <user id="1">
    <name>Wonder Woman</name>
  </user>
  <user id="2">
    <name>Black Panther</name>
  </user>
</users>
```

**Choices**:
1. No, this is XML. *
2. No, `users`, `name,` and `user id` all need to be inside quotation marks.
3. No, there should be curly braces around each attribute.
4. No, this is HTML.

**Explanation**: This is XML. XML uses opening and closing tags, just like HTML.

---
**Prompt**: After successfully performing a `fetch()` and before doing any extra processing, Siya now has this JSON in her code. Did Siya define the attribute `name`?

```json
{
  "users": [
    {"name": "Superman", "id": 0},
    {"name": "Wonder Woman", "id": 1},
    {"name": "Black Panther", "id": 2}
  ]
}
```

**Choices**:
1. Yes, Siya defined it when she parsed the serialized data to JSON.
2. Yes, Siya defined it as the field attribute when she called the API; `id` is the only attribute that the API provided.
3. No, `name` is the title of an attribute returned by the API web server. *
4. No, `name` was automatically assigned by the browser when it recognized the value format.

**Explanation**: Parsing the JSON from a `fetch()` call simply returns and formats information from the remote API web server. `name` was an attribute passed into her program by the API web server.

---
**Prompt**: Every browser supports `fetch()`, which is why it's so readily used in JavaScript.

**Choices**:
1. True
2. False *

**Explanation**: Not every browser supports `fetch()`. ES6 is a standard, but not all browsers have adopted it (notably, Internet Explorer has not). Check which browsers you wish to support before using any ES6 syntax or keywords.

---
**Prompt**: When using an API key, you make a standard `fetch()` request to the API. The remote web server then requests the key, which you return in a second `response()` call.

**Choices**:
1. True
2. False *

**Explanation**: When using an API key, you need to include the key in your initial request. For example, if your key to the OpenWeather API is `052f26926ae9784c2d677ca7bc5dec98`, you need to include that in the initial `fetch()` URL: `http://api.openweathermap.org/data/2.5/weather?zip=60614,us&appid=052f26926ae9784c2d677ca7bc5dec98`.
