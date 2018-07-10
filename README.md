# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Instructors' Guide to the React Module

- **Note 1**: The term "React Module" refers to all 8 React repos taught sequentially.

- **Note 2:** No links open in a new tab. I don't know why - embedding HTML didn't work. If you can fix it, let me know.

- **Note 3:** List and link to all repos is the `list-of-repos.md` in this folder.

#### Here are likely daily timings
- These timings are estimates based on the pilot cohorts. **I recommend you allot five days to account for overflow and questions.** If your timings are very different than below, please let me know so I can change it.
- *Note: Lessons with <sup>1</sup> have 1-2min videos.*

|                                                                **Day 1**                                                                	|                                                     **Day 2**                                                     	|                                        **Day 3**                                        	|                                         **Day 4**                                        	|
|:---------------------------------------------------------------------------------------------------------------------------------------:	|:-----------------------------------------------------------------------------------------------------------------:	|:---------------------------------------------------------------------------------------:	|-----------------------------------------------	|
| [:25] [Introduction<sup>1</sup>; and Initial Setup.](../../../react-intro)                                                                        	|  [:30] [ES6; ES6 Const/Let; ES6 Arrow Functions; ES6 Literals; and ES6 Exercise](../../../react-es6-functional) 	| [:20] [Declarative vs Imperative Programming](../../../react-apis-heroku-declarative) 	| [Self Project](../../../react-self-project) 	|
| [:35] [Components and JSX<sup>1</sup>](../../../react-intro)                                                                         	|         [:15] [Functional Components<sup>1</sup>; and Functional Components Exercise](../../../react-es6-functional)        	|                                [:30] [Heroku](../../../react-apis-heroku-declarative) 	|                                               	|
| [:15]  [Virtual DOM<sup>1</sup>](../../../react-intro)                                                                                     	|                            [:30] [Component Lifecycle](../../../react-es6-functional)                           	|                                       [:15] [*Optional*: Quiz 5](quizzes/quiz-5-after-heroku.md) 	|                                               	|
| [:30] [Props<sup>1</sup>; and Multiple Props](../../../react-intro)                                                  	| [:10] [Unidirectional Flow<sup>1</sup>](../../../react-es6-functional)                                                      	| [:30] [Film Exercise 4 - APIs](../../../react-apis-heroku-declarative)     	|                                               	|
| [:30] [Props Challenge (Blog project)](../../../react-intro)                                                                          	| [:20] [Immutable Data Types](../../../react-es6-functional)                                                     	| [1:00] [ATM Lab](../../../react-atm)                                                  	|                                               	|
| [:30] [Nested Components; and Nested Components Challenge (Blog project)](../../../react-intro)                                       	| [:15] [Section Summary](../../../react-es6-functional) and [*Optional*: Quiz 3](quizzes/quiz-3-after-immutable-data.md)      	| [1:00] [Tic Tac Toe Exercise](../../../react-tictactoe)                              	|                                               	|
| [:20] [Section Recap; and LoTR Codealong / Exercise](../../../react-intro)                                                              	| [:30] [[Optional] Film exercise - unidirectional flow](../../../react-es6-functional)                           	| [:20] [Documentation](../../../react-documentation)                                   	|                                               	|
| [:15] [*Optional*: Quiz 1](quizzes/quiz-1-after-LoTR.md)                                                                            	| [:25] [Browser History Mechanics](../../../react-router) 	| [:30] [Documentation Group Exercise](../../../react-documentation)                    	|                                               	|
| [:20] [*Optional*: Film Exercise - Components](../../../react-intro). *Note: Uses ES6*       	| [:25] [Router intro<sup>1</sup>; all of dentist codealong](../../../react-router)                                           	|                                                                                         	|                                               	|
| [:30] [State<sup>1</sup>; and State Exercise (Blog Project)](../../../react-state-exercises)                                                      	| [:30] [Router Blog Exercise](../../../react-router)                                                             	|                                                                                         	|                                               	|
| [:10] [Component Lifecycle](../../../react-state-exercises)                                                                           	| [:10] [*Optional*: Quiz 4 - Router](quizzes/quiz-4-after-router-exercise.md)                                                        	|                                                                                         	|                                               	|
| [:30] [ToDo Exercise](../../../react-state-exercises)                                                                                 	| [:30] [APIs; Data Types; Fetch](../../../react-apis-heroku-declarative)                                         	|                                                                                         	|                                               	|
| [:10] [Recap<sup>1</sup>](../../../react-state-exercises). -- **Note**: After this, be sure students have an idea when and when not to use React. 	| [:30] [API Project (Blog Project)](../../../react-apis-heroku-declarative)                                                	|                                                                                         	|                                               	|
| [:30 or Homework] [Calculator Exercise](../../../react-state-exercises)                                                              	|                                     	|                                                                                         	|                                               	|
| [:15] [*(EOD if calc is hw).* *Optional*: Quiz 2](quizzes/quiz-2-after-calculator.md)                                                                	|                                                                                         	|                                                                                         	|                                               	|
| [[Homework *Day 2 if calc is hw*]. *Optional* Film Exercise - State](../../../react-state-exercises). Note: Uses ES6.*                    	|                                                                                                                   	|                                                                                         	|                                               	|

## Optional Quizzes and Review Guides

- **Quizzes**:. There are optionally short, ten question quizzes after each repo. The quiz questions and links are in the `quizzes` folder.
  - These are not referenced in anything student facing and can optionally be assigned at your discretion.
  - **Note:** The review guides are linked at the end of the quizzes, but the link is incorrect (as this is in staging on myGA, it's not an easy fix). You can choose instead to share the review guide from the review guide repo.

- **Review Guides**: There are optionally review guides for a student to quickly reference in the future. These are located in [the `react-review-guides` repo](../../../react-review-guides/).
  - These are not referenced in anything student facing and can optionally be shared at your discretion.

## Solution Locations
- Solutions to exercises are on branches within their respective repos.
  - One exception is the Functional Components To-Do in the ES6 repo; the solution is in the subsequent .md file.
- Solutions to the blog project that's built throughout the class are in branches in the [`react-blog-project` repo](../../../react-blog-project).
- Solutions to the film project that's built throughout the class are in branches in the [`react-film` repo](../../../react-film).

## Important Notes on the Film Exercise
- There is a film exercise that is built upon throughout the class.
- Please note that this exercise has some advanced JavaScript and starts out using ES6 (`const`, `let`, and arrow functions) before ES6 is explained in Unit 3.
  - Alternate option: After ES6 is taught, assign film exercises 1-3 together.
- Dedicate time each morning to go over and explain the solution.
- The film exercises are not referenced anywhere else in the class and can safely be ignored if you so choose.

## Options on ways to teach the React Module

- **Option 1**: Teach it like a normal class, entirely in classroom.
  - Follow the schedule above.


- **Option 2**: Teach flipped classroom
  - This means assigning as much reading as possible for homework; all exercises and codealongs during the day.
  - For a schedule on teaching React flipped, follow the `flipped-classroom-schedule.md`.


- **Option 3**: Teaching ES6 first, before React.
  - [ES6 is part of unit 3](../../../react-es6-functional/) - the `react-es6-functional` repo.
  - If you'd like to teach ES6 before you start React, you will teach lessons 1-6 of unit 3 before starting back at unit 1 for the rest of the React module
      - **Note**: `02-ES6-ConstLet.md` has a thought exercise near the end that refers to a blog students do in unit 2 and has JSX in it, so it might be confusing if you haven't started React first.
  - If the students already know ES6, you can skim over these lessons - lesson 6 has a helpful recap you might want to do.
  - **Note**: Units 1 and 2 do not use most standard ES6 (`const`, `let`, arrow functions) as it's not designed to be taught until unit 3, so you'll need to give your students a headsup that you went out of order (to avoid the question "Why is this all `var`?").
