---
title: React Full-Stack
type: lesson
duration: "6:00"
creator:
    name: Jamie King
    city: ATL
competencies: Full-Stack Applications
---
 
 # ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Code-Along: Idea Board 

---

Let's build an idea board!

### Objectives
*After this lesson, students will be able to:*
- Use MongoDB and Mongoose to persist data to be served to a React UI.
- Build an Express server that serves information in a JSON format.
- Connect API to React via `axios`
- Deploy the full stack application to Heroku

---

![idea board](https://slack-imgs.com/?c=1&url=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*SMKZC-Ej73wFOmqNT-JQ7Q.gif)

<aside class="notes">

**Teaching Tips**:
- These first three slides (learning objectives, image of solution, and good luck meme) are for you to project to the class as you introduce the topic. The remainder of this lesson is an instructor-facing script. 
- The image of the solution here is so the class can see the end product and have an idea of what they are building.

</aside>

---

![you got this](assets/you-got-this-meme.png)

<aside class="notes">

**Teaching Tips**:

- At this point you can stop projecting these slides and begin to project the code. The remainder of this lesson is a script for instructors (not student-facing slides).

</aside>

---

**This readme serves as the instructor notes/prep for the MERN stack idea board app. This is not a student-facing document.**

## Getting Started

This code-along guides students to building a full-stack application with the MERN stack. Estimated class time to complete the code-along is 6 hours.

You can have students start the project in github instead of locally just to show an alternative way of getting a project up and running. If so, you can start out the code-along like so:

Go ahead and create a repo on github called `idea-board`. Make sure to include the `.gitignore` for Node apps and a `README`.

After creating the repo, go ahead and clone it locally into your class-exercises folder.


## Express Set Up
Today, we're going to use the express generator to create everything we need to run our basic express server

```
express --no-view
npm i
touch server.js
```

## Modifying app.js
In our `app.js` file, we see all the basics that an express server needs to run! However, we are missing a few things that *we* need to get our server running. Notably absent are `dotenv`, `mongoose`, and `bodyParser`.  As our needs grow, we will refactor and build onto the file, but for now lets use the following setup:

```
npm i dotenv mongoose
```

```js
require("dotenv").config();
var express = require('express');
var path = require('path');
var logger = require('morgan');

const mongoose = require('mongoose');
mongoose.Promise = global.Promise;
mongoose.connect(process.env.MONGODB_URI); //mongodb://localhost/idea-board

const connection = mongoose.connection;
connection.on('connected', () => {
  console.log('Mongoose Connected Successfully');
});
// If the connection throws an error
connection.on('error', (err) => {
  console.log('Mongoose default connection error: ' + err);
});

var indexRouter = require('./routes/index');
var usersRouter = require('./routes/users');

var app = express();

app.use(logger('dev'));
app.use(express.json());
app.use(express.urlencoded({ extended: false }));
app.use(express.static(path.join(__dirname, 'public')));

app.use('/', indexRouter);
app.use('/users', usersRouter);

module.exports = app;

```

Let's start our app and test that it is working.

> COMMIT!

## Integrating create-react-app
Before we start working building out our models and controllers, let's first connect our Express app to React. Use `create-react-app` to get our UI up and running.
```bash
# Inside of Idea-Board
create-react-app client
```

Your folder structure should now look something like this.
```
|- client
  |- node_modules
  |- public
  |- src
  |- package.json
  |- ...
|- node_modules
|- app.js
|- package.json
...
```

This will create a new React application for us to begin building our game.  Let's try to start our application.

**OH NO!**
You may have gotten an error that looks something like this:
```bash
? Something is already running on port 3000. Probably:
  node server.js
  in /path_to_directory/Idea-Board
Would you like to run the app on another port instead? (Y/n)
```

Webpack uses the port 3000 when ever we start our application.  This conflicts with our Express server that is also attached to port 3000.  In order to fix this, we will change our Express app to listen on 3001.

Now we can run both servers at the same time. We can do that by starting our server in one window and our React app in another.  However, there is a tool we can use to run both of these servers within the same window.

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
  "start": "node bin/www",
  "dev": "concurrently \"nodemon bin/www\" \"cd ./client  && npm start \" ",
  "test": "echo \"Error: no test specified\" && exit 1"
},
...
```

Now we can run `npm run dev` and our application will start on both port 3000 and 3001! Let's verify both are working by visiting both ports in the browser.

> COMMIT

## Deploying The App
Now that we have an extremely basic Express and React app, let's go ahead and deploy early.  This will be similar to the way we previously deployed server-rendered apps, but with a couple additional steps.

### Building a Production React App
When we develop React Apps, we use a bunch of extra tools that are unnecessary for a production environment (auto-reloading, error messaging, dev server, etc).  When we are ready to push our app into production, we can use a special script to get a prod ready version of our app.

Within our client folder, we can run a command called `npm run build`.  This will take all of the code that we've been running through webpack and bundle it all into a minified build ready for production deployment.  That will live inside a `build` directory.

After we build the app, we need to let Express know that it needs to be aware of the new static files. Finally, we need to make a get route at the index that will serve the `index.html` of the built production React app.

```js
// inside of server.js
...
  app.use(express.static(__dirname + '/client/build/'));
...
  app.get('/', (req,res) => {
    res.sendFile(__dirname + '/client/build/index.html')
  })
...
```

We can test the production app now, by running `node server.js`.  If our app looks like what we intend, then we can proceed with deploying our app.

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
    "start": "node bin/www",
    "dev": "concurrently \"nodemon bin/www\" \"cd ./client  && npm start \" ",
    "test": "echo \"Error: no test specified\" && exit 1",
    "postinstall": "cd client && npm install && npm run build"
  },
...
```

Now we can proceed our Heroku deployment like normal.

```bash
heroku create inclass-idea-board
heroku addons:create mongolab:sandbox
git add -A
git commit -m "commit message"
git push heroku master
```

## Setting up a Database
Now that we've verified that we can run both apps at the same time and gotten the basic app up on Heroku, let's start building out the Schemas for our database.

Today's example app is going to have 2 Models. User and Idea

### Create a New Directory
Create a new directory called `db` and create a `schema.js` within there. Create a Mongoose model for each model.

* User has name, password(string), and ideas.
* Idea has title, description, and created(Date)
  * Make sure the default value for title and description is something similar to "New Title" and "New Description"

**Take a look at [this sample project Two](https://github.com/dphurley/sample_project_two) if you need a refresh on how to do this**

> COMMIT

## Seed Data
Now that we have out 2 models, let's go ahead and supply some seed data.  Let's populate a seeds file with one User with a few ideas.

```js
require('dotenv').config()
const mongoose = require('mongoose')
mongoose.connect(process.env.MONGODB_URI, {useMongoClient: true})
mongoose.Promise = global.Promise

const { User, Idea } = require('./schema')

const mars = new Idea({
  title: 'Fly to Mars',
  description: "Earth isn't Red enough. Let's move to a new planet"
})
const tesla = new Idea({
  title: 'Build a Car',
  description: "Gas is too expensive. I'm gonna build a car that doesn't need gas"
})
const elon = new User({
  userName: 'elon_musk',
  password: 'spaceiscool',
  ideas: [mars, tesla]
})

User.remove({})
  .then(() => elon.save())
  .then(() => console.log('Successful Save'))
  .then(() => mongoose.connection.close())
```

Next we run `node db/seeds.js` to populate our database.  Now we finally have enough info to build out our API.

> COMMIT

## Building an API
Now that we have data within our database, let's use Express to retrieve that info and serve it as JSON for our React app to consume.  In order to do that, we need to use Express Router to build routes for our API. This is going to look similar to the server side rendered controllers we built in the past, but with one major difference.

```js
// ./server.js
  app.use('/api/users', UsersController)
  `
// ./controllers/users
const express = require('express')
const { User } = require('../db/schema')
const router = express.Router()

router.get('/', (req, res) => {
  User.find().then(users => {
    res.json(users)
  })
  .catch((err) => console.log(err))
})

...

module.exports = router;
```

Now if we check our route at `localhost:3001/api/users` we should see that we get a JSON object back.  We are able to get this JSON object by using `res.json` instead of `.render` or `.send`.

We can now retrieve the user that we created in our seeds.  This gives us enough to get started on building the UI for out idea-board.
We will need to build more routes later in the app, but this will work for the moment. (YAGNI!)

> COMMIT
> DEPLOY

### Scaffolding out our Idea Page UI.
For the UI of our game, lets get started by building out a client side router using `react-router`. We'll also install our other dependencies

```bash
# inside of client directory
npm i react-router-dom axios styled-components
```
To start, our app will have 3 separate views:
  - `HomePage`
  - `LogInPage`
  - `IdeaPage`

Within our `components` folder, we will go ahead and create a basic component for each route.  Once these are created, we can add React Router to the `App.js` component.

```jsx
import React, { Component } from 'react'
import { BrowserRouter as Router, Route, Switch, Link } from 'react-router-dom'
import styled from 'styled-components'
import HomePage from './components/HomePage'
import LogInPage from './components/LogInPage'
import IdeaPage from './components/IdeaPage'

class App extends Component {
  render () {
    return (
      <Router>
        <div>
          <div>
            <Link to='/login'>Login</Link>
          </div>
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

We can add route params to our client side routes, much like what we've seen when working in Express.  The value defined will be passed in props.  For example, the above Route param will be available as `props.match.params.userId`.

> COMMIT

## Creating the Home and LogIn Route

The first thing we'll focus on in the UI is the page users will see when they first load the page. On this page, we want to encourage a user to visit the LogIn page or Ideas page. We will start to make API calls once we build out the LogIn page.

## Create the Home Page Element
Create the home page element with a greeting and a `Link` to the LogIn component.  Make sure to also add a `Link` back to home on LogIn

## LogIn

In order to make API calls, we'll use Axios.

```jsx
import React, { Component } from 'react'
import { Redirect } from 'react-router-dom'
import axios from 'axios'

class LogIn extends Component {
  state = {
    users: []
  }

  getAllUsers = () => {
    axios.get('localhost:3001/api/users').then(res => {
      this.setState({users: res.data})
    })
  }
  
  render () {
    return (
      <div>
        <h1>Log-In</h1>
        <h3>Please Select an Existing User</h3>
        {this.state.users.map(user => {
          return (<Link to={`/user/${user._id}`}>{user.userName}</Link>)
        })}
      </div>
    )
  }
}

export default LogIn
```

Unfortunately, when we load our UI we get an error!

```text
XMLHttpRequest cannot load localhost:3001/api/game. Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, https.
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

```js
  router.post('/', (req, res) => {
    const newUser = new User(req.body.user)
    newUser.save().then((user) => {
      res.json(user)
    }).catch(console.log)
  })
```

Now we are able to add a Sign-Up form to the LogIn page.

```js
  createUser = () => {
    axios.post('/api/users', {
      user: this.state.user
    }).then((res) => {
      this.setState({redirectToHome: true, createdUser: res.data})
    })
  }

  handleChange = (e) => {
    const user = {...this.state.user}
    user[e.target.name] = e.target.value
    this.setState({user})
  }

  handleSignUp = (e) => {
    e.preventDefault()
    this.createUser()
  }
...
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
```

Finally we need to create a conditional that will handle a redirect after a user is successfully saved.

> COMMIT

## Building A Static Idea Board

Now that we are able to navigate to the `IdeaView` page, we can now focus on building out some static views.  Let's mock some data in the initial state and write some starter JSX.

```jsx
import React, { Component } from 'react'
import axios from 'axios'
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
          {ideas.map(idea => {
            return (
              <div>
                <input type="text" name="title"/>
                <textarea name="description"/>
                <button>Delete Idea</button>
              </div>
            )
          })}
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

We now have complete static code that is styled and living in small components with props being passed down from the `IdeaView`.  Now we need to connect the info from our API to the state.

Since we are using React Router to create a route that matches `/user/:userId` we can take advantage of props that are being passed from the library in the form of `props.match.params.userId`.  Let's tell React to call our API if the props are passed down correctly.

```js
  router.get('/:id', (req, res) => {
    User.findById(req.params.id).then((user) => {
      user.ideas = user.ideas.reverse()
      res.json(user)
    }).catch(console.log)
  })
```

**Why did we call `.reverse`? This means that our response from the api will show our newest ideas first**

```js
...
  componentWillMount () {
    if (this.props.match.params) {
      const { userId } = this.props.match.params
      axios.get(`/api/users/${userId}`).then(res => {
        const user = {
          _id: res.data._id,
          userName: res.data.userName
        }
        const ideas = res.data.ideas
        this.setState({user, ideas})
      })
    }
  }
...
```

As long as our props are being passed down properly, we should now see info coming in from our API.

> COMMIT
> DEPLOY

**Do you not see any data?  Try running `heroku run node db/seeds.js`**

## Adding Click Event to Create New Post
Next up, let's add a click event to the `New Post` button.

```js
//IdeaController
router.post('/', (req, res) => {
  User.findById(req.params.userId).then((user) => {
    const newIdea = new Idea({})
    user.ideas.push(newIdea)
    user.save().then((user) => {
      res.json(newIdea)
    })
  })
})
```

```js
  createIdea = () => {
    axios.post(`/api/users/${this.state.user.id}/ideas`).then(res => {
      const newIdeas = [...this.state.ideas]
      newIdeas.unshift(res.data) //This will add the new Idea to the beginning of the array
      this.setState({ideas: newIdeas})
    })
  }
  ...
  <button onClick={this.createIdea}>New Idea</button>
```

## Write Code to Delete an Idea
We will write similar code to delete an idea.  Work with the student's around you to write an Express route, create a custom method, and pass it down through props.

Hint: You will need one argument
```js
  deleteIdea = (idea) => {//Your code here}
```

> COMMIT

### Handling Form Changes
We can create empty ideas and delete those ideas, now we have the task of updating information and saving it to our server.  That means that we will need to work with forms!

Let's focus on creating a handleChange event to update our local state.

```js
...
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

First, we'll add a route to the IdeasController
```js
// /api/user/:userId/ideas/:id
router.patch('/:id', (req, res) => {
  User.findById(req.params.userId).then((user) => {
    const update = req.body.idea
    const idea = user.ideas.id(req.params.id)
    if (update.title) {
      idea.title = update.title
    }
    if (update.description) {
      idea.description = update.description
    }
    user.save().then((user) => {
      user.ideas = user.ideas.reverse()
      res.json(user)
    })
  })
})
```

Next, we will add a method that will trigger the patch and update the local state. This will look pretty similar to our last method.
```js
  updateIdea = (idea, e) => {
    axios.patch(`/api/users/${this.state.user.id}/ideas/${idea._id}`, {idea}).then(res => {
      this.setState({ideas: res.data.ideas})
    })
  }
```

Finally, let's tie this event to an individual idea.  We COULD attach that to a button and have a boring old onClick event, but let's try something new.

## Check Documentation
Check out the [Synthetic Event docs](https://reactjs.org/docs/events.html) and find the event that allows us to trigger the update whenever a user leaves an input.

> COMMIT
> DEPLOY

We did it! We now have an app that updates our ideas in real time.  And through using React, we built it in a scalable and easy to read way.

## Further Reading:

* [Using `create-react-app` with a server](https://www.fullstackreact.com/articles/using-create-react-app-with-a-server/)
* [94 Examples of Fullstack React Apps](https://react.rocks/tag/FullStack)
