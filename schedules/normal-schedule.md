Note: anything that says "exercise", the student can also just self study in class (as some of it has videos). Most lessons have code that the student needs to follow along with. Assume if there is code on screen and it's not stated otherwise ("You do"), the student will be following along with you.

----
## General breakdown:

- There are 5 lesson repos to go through sequentially. These have lectures, exercises, and projects. See previous readme
- Then, there are 2 lab repos where students are given an existing code base and told to add a feature.
- Then, there is 1 lesson repo - which has a group exercise.
- Then, there is 1 self project, which takes an entire day.

This is a total of 9 repos over 4 days. This has no homework. See below for breakdown.
  - **Note**: Allot a fifth day for bleed over in case of many questions.
  - If enough instructors tell me (Susi) timings are significantly off, I'll change it, so let me know.
- There are also optional quizzes, as per the `quizzes` directory of this repo. The quizzes say on them where they go.
- Note: Some instructors have assigned the lessons with videos as homework instead of having them work on it during the day.
- If you really like homework, see the "flipped classroom" schedule.

----

## Daily breakdown by repo:

- Here are likely daily timings. If enough instructors tell me (Susi) this is off, I'll change it, so let me know. The same applies to specific timings below.
  - Repos 1, and Repo 2 through lesson 5.
    - Intro to React through state
  - Rest of repo 2, Repos 3 and 4 will be day 2.
    - ES6, functional components, component lifecycle, Router
  - Repos 5 - 8 will be day 3.
    - APIs, imperative vs declarative programming, Heroku, two exercises where students clone existing repos, and documentation.
  - Repo 9 is day 4.
    - Entirely a self project.

------

## Specific repo links, timings, and notes:

#### [Repo 1: react-intro](https://git.generalassemb.ly/education-product/react-intro).
**Timing:** ~ 4 hours total ~2.5 hours through lesson 9; ~1.5 hrs through end of repo; ~15 min for quiz.
**Topics:** This covers components, JSX, the virtual DOM, and props.

Run through the repo in order. Notes on particular lessons to call out:
- Lesson 1 has:
  - a video
- Lesson 3 has:
  - a video
  - a short exercise where students will need a piece of paper to draw out components
- Lesson 5 has:
  - a video
  - a very quick exercise (10 min) for students to try and figure out on their own. The solution is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/blob/master/exercises/jsx-hello-world/App.js).
- Lesson 6 has:
  - a video.
- Lesson 7 has:
  - a video.
- Lesson 10:
  - Is the first of the blog projects.
  - The student does this individually.
  - The solution code is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/projects/project-01-jsx). This is a public repo.
- Lesson 12:
  - Is the second of the blog projects.
  - This builds off the previous project. Students do not need starter code.
  - The student does this individually.
  - The starter code (for you or lost students) and solution code is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/projects/project-02-nested-components). This is a public repo.
- Lesson 14 (LoTR codealong):
  - This can be an assigned exercise or a codealong. It builds a simple React app from scratch.
  - The solution is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/exercises/lord-of-the-rings/src).


- [Quiz 1 is here](https://git.generalassemb.ly/education-product/react-instructor-notes/blob/master/quizzes/quiz-1-after-LoTR.md)
  - **is optional** at the end of this repo.

#### [Repo 2: react-state-exercises](https://git.generalassemb.ly/education-product/react-state-exercises).

**Timing:** ~5 hrs total. Lessons 1-3; 1.5 hours. lessons 4 - 5: 1.5 hours. Lessons 6 - 7: 1.5 hours together. Quiz 2: 15 min.
**Topics**: This covers state and has two recap exercises.

Run through the repo in order. Notes on particular lessons to call out:

- Lesson 1 - State
  - has a video.
  - has a quick exercise at the end. The solution is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/blob/master/exercises/state_wrap_10/App.js)
- Lesson 2 - State Project
  - Is the third of the blog projects. This has a bonus activity as well.
  - The student does this individually.
  - This builds off the previous project. Students do not need starter code.
  - Starter code (for you or lost students) and solution code is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/projects/project-03-state). This is a public repo.
- Lesson 4 - ToDo Exercise
  - An exercise to build a todo list from scratch. Can be a codealong or a self exercise for students.
  - Recommended as a codealong, where you go through it with students.
  - No solution code - it continues in the next file.
- Lesson 5 - ToDo Exercise Continued
  - Continues the above ToDo List.
  - A solution is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/exercises/to-do-list)
- Lesson 6 - Recap
  - Best practices up to this point. Has a video.
- Lesson 7 - Calculator Exercise
  - Exercise for students to go through on their own.
  - Has a bonus at bottom.
  - Solution is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/exercises/calculator)


- [Quiz 2 is here](https://git.generalassemb.ly/education-product/react-instructor-notes/blob/master/quizzes/quiz-2-after-calculator.md)
  - **is optional** at the end of the repo.


#### [Repo 3: react-es6-functional](https://git.generalassemb.ly/education-product/react-es6-functional).
**Timing:** ~2.5 hours. ~1hr if skipping ES6. ~15min for quiz.
**Topics:** This covers ES6, functional components, and component lifecycle. All ES6 exercises are in linked CodePens.

Run through the repo in order except:
  - **If students already know ES6**, you can skip to lesson 6 or 7. Lesson 6 is an ES6 recap and CodePen exercise - it's recommended for review but not necessary if you're confident in the students' abilities.

Other notes:
- Lesson 8 - Functional Component Exercise
  - A very simple exercise. Let students think about it.
  - Solution is next lesson
- Lesson 8.5 - Function Component Solution
  - Solution and explanation to the previous part of lesson 8
- Lesson 10 - Unidirectional Flow
  - Has a video
  - Has a quick exercise in codepen about halfway down.
    - Solution codepen with explanation is immediately after.


- [Quiz 3 is here](https://git.generalassemb.ly/education-product/react-instructor-notes/blob/master/quizzes/quiz-3-after-immutable-data.md).
  - **Optionally**, can be given at end of lesson.

#### [Repo 4: react-router](https://git.generalassemb.ly/education-product/react-router).
**Timing:** ~3hrs. ~1/2 hr for lessons 1-4; ~1 hr for lessons 5-7; ~1 hour for lesson 8; 10min for quiz.
**Topics**: This covers single page applications, browser history mechanics, and React Router.

Run through the repo in order. Notes on particular lessons to call out:

- Lesson 4:
  - Has a video
- Lessons 5, 6, and 7:
  - are a codealong to build a dentist website. Do this with the student.
- Lesson 8:
  - Is the fourth of the blog projects.
  - Students do this on their own.
  - The starter code (for you or lost students) and solution code is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/projects/project-04-router)


- [Quiz 4 is here](https://git.generalassemb.ly/education-product/react-instructor-notes/blob/master/quizzes/quiz-4-after-router-exercise.md).
  - **Optionally**, can be given at end of lesson.


#### [Repo 5: react-apis-heroku-declarative](https://git.generalassemb.ly/education-product/react-apis-heroku-declarative).
**Timing:** 3 hours. Breakdown: 1 hr lessons 1-4; 1 hr lesson 5, 1 hr lesson 6 and 7. ~15min quiz.
**Topics**: This covers APIs, `fetch()`, imperative and declarative programming, and Heroku.

Run through the repo in order. Notes on particular lessons to call out:
- Lesson 4:
  - Is a codealong for a Shakespeare API. Do it with them.
- Lesson 5:
  - Is the fifth of the blog projects.
  - Students do this on their own.
  - The starter code (for you or lost students) and solution code is [here](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/tree/master/projects/project-05-fetch)



- [Quiz 5 is here](https://git.generalassemb.ly/education-product/react-instructor-notes/blob/master/quizzes/quiz-5-after-heroku.md).
  - **Optionally**, can be given at end of repo.


#### [Repo 6: ATMReact](https://github.com/susiremondi/ATMReact). Timing: 1 hour.
This is a lab to assign to students. It's an existing ATM application that they will add a feature to. It's very simple; the goal is to introduce them to reading existing code.
  - The repo readme has instructions on it, so you can point students to it and optionally run over the instructions with them.
  - Note: Hosted on Susi's regular github. Eventual plan to clone over.

#### [Repo 7: tictacReact](https://github.com/susiremondi/tictacReact). Timing: 1 hour.
This is a more complicated lab - an existing tic tac toe application. They add a feature to it. This is the same tic tac toe exercise in the Facebook tutorial, which segues to the next repo.
  - The repo readme has instructions on it, so you can point students to it and optionally run over the instructions with them.
  - Note: Hosted on Susi's regular github. Eventual plan to clone over.

#### [Repo 8: react-documentation](https://git.generalassemb.ly/education-product/react-documentation).
**Timing:** 1 hour. (1/2 hr per lesson)
**Topics:** This explores the React documentation on Facebook in detail.
- Lesson 1:
  - Has an exercise at the button for students to walk through. The solution is linked below that in a CodePen.
    - If enough instructors ask, I will move this solution from the CodePen into the solution repo so it isn't on the page.
- Lesson 2:
  - Is a group exercise for students to research in the documentation, then give a presentation.

#### [Repo 9: Self project.](https://git.generalassemb.ly/education-product/React-Exercise-Solutions/blob/master/self-exercise/react-self-exercise.md). Timing: 1 day.

This is only a prompt which is a self project. This takes an entire day; students build their own website (or try to copy one like airBnB) from scratch. It includes researching a new topic on their own and adding that functionality.
  - Note: This link is in the `React Exercise Solutions` repo, so if they're curious and poke around, they will find all previous exercise and project solutions from the class.
