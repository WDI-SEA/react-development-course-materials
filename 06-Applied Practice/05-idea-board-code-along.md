 # ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Code-Along: Idea Board 


### Objectives
*After this lesson, you will be able to:*
- Use MongoDB and Mongoose to persist data to be served to a React UI.
- Build an Express server that serves information in a JSON format.
- Connect API to React via `axios`
- Deploy the full stack application to Heroku

<aside class="notes">

**Talking Points**:

A lot of modern JavaScript is focused on knowing the right tools for the job.  Today we will be pulling in everything we've learned about Node and React to build a full stack application using the MERN stack.

</aside>

-------

## MERN Stack

MERN stack -  shorthand way of saying that an application is a full-stack Java Script app. 

**M**ongoDB

**E**xpress

**R**eact

**N**ode



<aside class="notes">

**Talking Points**:

When you see MERN stack, this is typically just a shorthand way of saying that the application is a full-stack JavaScript app.  The tools that we use for MERN apps are: Mongo (MongoDB), Express, React, and Node.  
While there are some boilerplate tools to build out a full MERN stack app, we are going to build our own using `create-react-app` and the Express and Mongo patterns we've used in the past.  This allows us to fully understand our application and prevents introducing a bunch of code that we haven't written and understand.

</aside>

--- 

## Idea Board

We will build an app where a user can write out different ideas and save them to a database.

This app will have 2 models- Users and Ideas (which will live inside of users)

Here's a GIF representation of the how this may look, though we will also add the ability for a user to 'log in'
![idea board](https://slack-imgs.com/?c=1&url=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*SMKZC-Ej73wFOmqNT-JQ7Q.gif)


<aside class="notes">

**Talking Points**:

- Today we are going to be taking advantage of the data persistance of an API and the single page polish that React brings!  Our app is an idea tracker where a user can write out different ideas and save them to a database.  Kind of like leaving post-it notes in the browser!

- This app will have 2 models - Users and Ideas (which will live inside of users)

- Here's a GIF representation of the how this may look, though we will also add the ability for a user to 'log in'

</aside>

--- 

## You Do: Data Model Brainstrom 

Work with classmates around you to: 
- Write out three user stories 
- Sketch two wireframes 
- Illustrate what our data model might look like. Think about the API routes that we will need. What components do you think we will need? What routes do we need to make available to the React app?


<aside class="notes">

**Teaching Tips**:
- read through activity directions
- set students off in their groups
- walk around and observe, help out, answer questions, provide input

**Note**: You will now transition from sharing the intro slides to sharing your text editor for the codealong. Refer to the readme titled: 06-full-stack-app-code-along.md for those notes.

</aside>
