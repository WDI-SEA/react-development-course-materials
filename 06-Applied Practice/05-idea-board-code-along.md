

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Code-Along: Idea Board

---

Let's build an idea board!

### Objectives
*After this lesson, you will be able to:*
- {Insert React Objectives Here}

<aside class="notes">

**Teaching Tip**:

- This is a brief interactive lecture that introduces the 6-hour Idea Board Code-Along.


**Talking Points**:

- This code-along guides you in building a mock up Full Stack Application with React.

- A lot of modern JavaScript is focused on knowing the right tools for the job.  Today we will be pulling in everything we've learned about React to build a full stack application.

</aside>

-------

## Idea Board

We are going to build our own Idea Board using `create-react-app` with a pre built backend server.  This allows us to fully understand our application and prevents introducing a bunch of code that we haven't written and understand.

</aside>

---

![idea board](https://slack-imgs.com/?c=1&url=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*SMKZC-Ej73wFOmqNT-JQ7Q.gif)

<aside class="notes">

**Talking Points**:
- We will build an app where a user can write out different ideas and save them to a database. This app will have 2 models — Users and Ideas (which will live inside of Users).


**Teaching Tips**:
- The image of the solution here is so the class can see the end product and have an idea of what they are building.

</aside>

---

## Data Model Brainstrom

Work with classmates around you to:
- Write out three user stories
- Sketch two wireframes
- Illustrate what our data model might look like. Think about the API routes that we will need. What components do you think we will need? What routes do we need to make available to the React app?


<aside class="notes">

**Teaching Tips**:
- Read through activity directions.
- Set students off in their groups.
- Walk around and observe, help out, answer questions, provide input.


</aside>

---

![you got this](assets/you-got-this-meme.png)

<aside class="notes">

**Teaching Tips**:

**The remainder of this document serves as the instructor notes/prep for the React stack idea board app. Do not project or share out the remainder of this document.**

</aside>

---

## Getting Started

This code-along guides students to building a React application with the create-react-app. Estimated class time to complete the code-along is 6 hours.

You can have students start the project in github instead of locally just to show an alternative way of getting a project up and running. If so, you can start out the code-along like so:

Go ahead and create a repo on github called `idea-board`. Make sure to include a `README`.

After creating the repo, go ahead and clone it locally into your class-exercises folder.

## Integrating create-react-app
Before we start working building out our models and controllers, let's first connect our server to React. Use `create-react-app` to get our UI up and running.
```bash
# Inside of Idea-Board
create-react-app client
cd client
```

## Server Set Up
Today, we're going to use a mock up server to run our basic react app.  Clone a copy of the server
```
# copy and paste into the main client folder we just created with create-react-app
git clone {github link to server.js} or d/l from github
npm install express
```
We will be using this file as a mock server for our React application.

Your folder structure should now look something like this.
```
|- node_modules
|- public
|- src
  |- App.js
|- package.json
|- server.js
|- ...
...
```

This will create a new React application for us to begin building our board.  Let's try to start our application.

Webpack uses the port 3000 when ever we start our application.  Our server will be running on 3001.

To run both servers at the same time. We can do that by starting our server in one window and our React app in another.  However, there is a tool we can use to run both of these servers within the same window.

## Concurrently

In order to run both our server and app at the same time, we are going to use an npm library called [`concurrently`](https://www.npmjs.com/package/concurrently). `concurrently` is going to allow us to run both our api server and webpack server at the same time.

```bash
# Inside idea-board directory
npm i concurrently
```
```json
//Inside package.json
...
"scripts": {
  "start": "react-scripts start",
  "dev": "concurrently \"node server.js\" \"npm start\" ",
  "test": "echo \"Error: no test specified\" && exit 1"
},
...
```


Now we can run `npm run dev` and our application will start on both port 3000 and 3001! Let's verify both are working by visiting both ports in the browser.

> COMMIT

Now if we check our route at `localhost:3001/api/users` we should see that we get a JSON object back.  We are able to get this JSON object by using `res.json` instead of `.render` or `.send`.

We can now retrieve the user that we created in our seeds.  This gives us enough to get started on building the UI for out idea-board.

### Scaffolding out our Idea Page UI.
For the UI of our game, lets get started by building out a client side router using `react-router`. We'll also install our other dependencies which you may choose to use for styling.  Examples will be using inline style.  Add additional styling to make it look better!

```bash
# inside of client directory
npm i react-router-dom styled-components
```
To start, our app will have 3 separate views:
  - `HomePage`
  - `LogInPage`
  - `IdeaPage`

Create a `components` folder and within , we will go ahead and create a basic component for each route.  Once these are created, we can add React Router to the `App.js` component.

```jsx
  import React, { Component } from 'react';
  import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
  import HomePage from './components/HomePage';
  import LogInPage from './components/LogInPage';
  import IdeaPage from './components/IdeaPage';

  class App extends Component {
    render () {
      return (
        <Router>
          <div style={{ textAlign: 'center'}}>
            <Switch>
              <Route exact path="/" component={HomePage}/>
              <Route path="/login" component={LogInPage}/>
              <Route path="/user/:userId" component={IdeaPage}/>
            </Switch>
          </div>
        </Router>
      )
    }
  }

  export default App
```

### Route Params in React Router

We can add route params to our client side routes.  The value defined will be passed in props.  For example, the above Route param will be available as `props.match.params.userId`.

> COMMIT

## Creating the Home and LogIn Route

The first thing we'll focus on in the UI is the page users will see when they first load the page. On this page, we want to encourage a user to visit the LogIn page or Ideas page. We will start to make API calls once we build out the LogIn page.

## Create the Home Page Element
Create the home page element with a greeting and a `Link` to the LogIn component.  Make sure to also add a `Link` back to home on LogIn

## LogIn

In order to make API calls, we'll use fetch.

```jsx
  import React, { Component } from 'react'
  import { Redirect } from 'react-router-dom'

  class LogIn extends Component {
    state = {
      users: [],
      user: null,
      redirectToHome: null
    }

    getAllUsers = () => {
        fetch('/api/users', { method: 'get' })
        .then((res) => {
            return res.json();
        }).then((json) => {
            this.setState({users: json.data});
        }).catch((err) => {
            console.log('error getting users', err);
        })
    }

    render () {
      return (
        <div>
          <h1>Log-In</h1>
          <h3>Please Select an Existing User</h3>
          {this.state.users.map(user => (
            <div key={user._id}>
                <Link to={`/user/${user._id}`}>
                    {user.userName}
                </Link>
            </div>
          ))}
        </div>
      )
    }
  }

  export default LogIn
```

Unfortunately, when we load our UI we get an error!

```text
XMLHttpRequest cannot load localhost:3001/api/users. Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, https.
```

This is an example of what's commonly referred to as a CORS error (Cross-Origin Resource Sharing)

### CORS
CORS is a mechanism that restricts API calls from domains that are outside of the domain from which the resource was initially served.  Basically this is a layer of protection for servers, because it prevents unwanted use of your API.

There are several ways that we can handle CORS requests, but for our app we are going to take advantage of the tooling provided by `create-react-app`.  We can add a "proxy" server to our React application, which will allow us to make requests that look they are coming from our current server but actually hit the server we define in the `package.json`

```json
...
"proxy": "http://localhost:3001",
...
```

**NOTE** When you add this proxy, you have to restart your server.  The auto-refresh will not pick up on the proxy addition.

> COMMIT

## Adding Sign-Up
Now that we can communicate between the server and client, let's expand our UserController and give it the ability to `post` a new User.

Now we are able to add a Sign-Up form to the LogIn page.

```js
  createUser = () => {
    fetch('/api/users', {
      method: 'POST',
      body: JSON.stringify(this.state.user),
      headers: { "Content-Type": "application/json; charset=utf-8" }
    }).then((res) => {
      return res.json();
    }).then((json) => {
      this.setState({redirectToHome: true, users: json.data, user: null});
    }).catch((err) => {
      console.log('error creating user', err);
    })
  }

  handleChange = (e) => {
    const user = {...this.state.user};
    user[e.target.name] = e.target.value;
    this.setState({user});
  }

  handleSignUp = (e) => {
    e.preventDefault();
    this.createUser();
  }
...
  <div>
    <h1>Sign-Up</h1>
    <form onSubmit={this.handleSignUp}>
      <div>
        <label htmlFor="userName">User Name</label>
        <input onChange={this.handleChange} name="userName" type="text" value={this.state.userName}/>
      </div>
      <div>
        <label htmlFor="password">Password</label>
        <input onChange={this.handleChange} name="password" type="text" value={this.state.password}/>
      </div>
      <button>Sign Up</button>
    </form>
  </div>
```

Finally we need to create a conditional that will handle a redirect after a user is successfully saved.

> COMMIT

## Building A Static Idea Board

Now that we are able to navigate to the `IdeaPage` page, we can now focus on building out some static views.  Let's mock some data in the initial state and write some starter JSX.

```jsx
  import React, { Component } from 'react'
  import styled from 'styled-components'

  class IdeaView extends Component {
    state = {
      user: {
        userName: 'Bob'
      },
      ideas: [{
        id: 1,
        title: 'hello',
        description: 'world'
      }, {
        id: 2,
        title: 'hola',
        description: 'mundo'
      }, {
        id: 3,
        title: 'goodnight',
        description: 'moon'
      }, {
        id: 4,
        title: 'greetings',
        description: 'earthlings'
      }]
    }

    render () {
      return (
        <div>
          <div>
            <h1>{this.state.user.userName}'s Idea Board</h1>
            <button>New Idea</button>
          </div>
          <div>
            {ideas.map(idea => (
                <div>
                  <input type="text" name="title"/>
                  <textarea name="description"/>
                  <button>Delete Idea</button>
                </div>
            ))}
          </div>
        </div>
      )
    }
  }

  export default IdeaView
```

## Add Styling

Now that we have the static starter code, let's clean things up and add some styling. Take the code above and refactor it into smaller components.  Next, use `styled-components` to add some styling to the page.  As a reminder, we ideally want our app to look something like this.

![idea board](https://slack-imgs.com/?c=1&url=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*SMKZC-Ej73wFOmqNT-JQ7Q.gif)

> COMMIT

## Bringing in User Info

We now have complete static code that is styled and living in small components with props being passed down from the `IdeaPage` to the `IdeaView`.  Now we need to connect the info from our API to the state.

Since we are using React Router to create a route that matches `/user/:userId` we can take advantage of props that are being passed from the library in the form of `props.match.params.userId`.  Let's tell React to call our API if the props are passed down correctly.


```js
...
  componentDidMount() {
      this.getUser();
  }

  getUser = () => {
    fetch(`/api/users/${this.props.match.params.userId}`, { method: 'get' })
    .then((res) => {
      return res.json()
    }).then((json) => {
      this.setState({user: json.data})
    }).catch((err) => {
      console.log('error getting user', err);
    })
  }
...
```

As long as our props are being passed down properly, we should now see info coming in from our API.

> COMMIT
> DEPLOY

## Adding Click Event to Create New Post
Next up, let's add a click event to the `New Post` button.

```js
  createIdea = () => {
    fetch(`/api/users/${this.state.user._id}/ideas`, { method: 'post' })
    .then((res) => {
        return res.json();
    }).then((json) => {
        this.setState({user: json.data});
    }).catch((err) => {
        console.log('error creating idea', err);
    })
  }
  ...
  <button onClick={this.createIdea}>New Idea</button>
```

## Write Code to Delete an Idea
We will write similar code to delete an idea.  Work with the student's around you to write an a custom method, and pass it down through props.

Hint: You will need one argument
```js
  deleteIdea = (idea) => {//Your code here}
```

> COMMIT

### Handling Form Changes
We can create empty ideas and delete those ideas, now we have the task of updating information and saving it to our server.  That means that we will need to work with forms!

Let's focus on creating a handleChange event to update our local state in the `IdeaView`.  We will be using lifecycle hooks to update the `IdeaView` everytime our state changes in the parent component.

```js
...
  state = {
      ideas: this.props.user.ideas
  }

  componentWillReceiveProps(nextProps) {
    if(nextProps.user.ideas !== this.state.ideas) {
        this.setState({ideas: nextProps.user.ideas});
    }
  }

  //We need to pass in multiple arguments here.  The first is the object of the specific idea that is being changed.
  //And the event object is the special event listener object that has information about the value and name
  handleChange = (idea, event) => {
    const newIdeas = [...this.state.ideas] //Here we use the spread operator to clone the array

    //Map through this cloned state and transform the specific idea that has been updated.
    const ideas = newIdeas.map((savedIdea) => {
      if (savedIdea._id === idea._id) {
        //Here we are using bracket syntax instead of dot-notation to transform a specific property
        //More info on bracket syntax here
        //https://medium.com/@prufrock123/js-dot-notation-vs-bracket-notation-797c4e34f01d
        savedIdea[event.target.name] = event.target.value
      }
      return savedIdea
    })
    this.setState({ideas: ideas})
  }
...
```

```js
<input onChange={(e) => handleChange(idea, e)}
  type="text" name="title" value={idea.title}/>
```

## Triggering an Update

The final step in our app is to create the ability to update an idea.

We will add a method that will trigger the patch and update the local state. This will look pretty similar to our last method.
```js
  updateIdea = (idea, e) => {
    // PATCH is case sensetive
    fetch(`/api/users/${this.state.user._id}/ideas/${idea._id}`,
        { method: 'PATCH',
        body: JSON.stringify(idea),
        headers: { "Content-Type": "application/json; charset=utf-8" }
    }).then((res) => {
        return res.json();
    }).then((json) => {
        this.setState({user: json.data});
    }).catch((err) => {
        console.log('error getting user', err);
    })
  }
```

Finally, let's tie this event to an individual idea.  We COULD attach that to a button and have a boring old onClick event, but let's try something new.

## Check Documentation
Check out the [Synthetic Event docs](https://reactjs.org/docs/events.html) and find the event that allows us to trigger the update whenever a user leaves an input.

> COMMIT
> DEPLOY

We did it! We now have an app that updates our ideas in real time.  And through using React, we built it in a scalable and easy to read way.

## Deploying The App
Now that we have an extremely basic Express and React app, let's go ahead and deploy early.  This will be similar to the way we previously deployed server-rendered apps, but with a couple additional steps.

### Building a Production React App
When we develop React Apps, we use a bunch of extra tools that are unnecessary for a production environment (auto-reloading, error messaging, dev server, etc).  When we are ready to push our app into production, we can use a special script to get a prod ready version of our app.

Within our client folder, we can run a command called `npm run build`.  This will take all of the code that we've been running through webpack and bundle it all into a minified build ready for production deployment.  That will live inside a `build` directory.

After we build the app, we can test the production app now, by running `node server.js`.  If our app looks like what we intend, then we can proceed with deploying our app.

Let's update the `package.json` to help Heroku understand more about our app.  We will add a script called `postinstall` which will instruct Heroku to execute the same steps to prepare the app as we took manually.

```js
...
  //Set the Heroku version of Node to the most recent available.
  "engines": {
    "node": "8.6.0"
  },
...
//Postinstall will install the client packages and build the minified UI in Heroku.

  "scripts": {
    "start": "node server.js",
    "dev": "concurrently \"node server.js\" \"npm start\" ",
    "test": "echo \"Error: no test specified\" && exit 1",
    "heroku-postbuild": "npm --production=false && npm run build"
  },
...
```

Now we can proceed our Heroku deployment like normal.

```bash
heroku create inclass-idea-board
git add -A
git commit -m "commit message"
git push heroku master
```

The application is now deployed!

> COMMIT
> DEPLOY

## Further Reading:

* [Using `create-react-app` with a server](https://www.fullstackreact.com/articles/using-create-react-app-with-a-server/)
* [94 Examples of Fullstack React Apps](https://react.rocks/tag/FullStack)
