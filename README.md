# Instructors' Guide to the React Module

Note 1: The term "React Module" refers to all 8 React repos taught sequentially.

Note 2: No links open in a new tab. I don't know why - embedding HTML didn't work. If you can fix it, let me know.

Note 3: List and link to all repos is the `list-of-repos.md` in this folder.

**Here are likely daily timings**. If enough instructors tell me (Susi) this is off, I'll change it, so let me know. The same applies to specific timings below.
- *Note: Lessons with <sup>1</sup> have videos.*

|                                                                **Day 1**                                                                	|                                                     **Day 2**                                                     	|                                        **Day 3**                                        	|                                         **Day 4**                                        	|
|:---------------------------------------------------------------------------------------------------------------------------------------:	|:-----------------------------------------------------------------------------------------------------------------:	|:---------------------------------------------------------------------------------------:	|-----------------------------------------------	|
| [:25] Introduction1<sup>1</sup>; and Initial Setup. -- *Repo: `react-intro`*                                                                        	|  [:30] ES6; ES6 Const/Let; ES6 Arrow Functions; ES6 Literals; and ES6 Exercise. -- *Repo: `react-es6-functional`* 	| [:20] Declarative vs Imperative Programming. -- *Repo: `react-apis-heroku-declarative`* 	| Self Project. -- *Repo: `react-self-project`* 	|
| [:25] Components; and Component Setup. -- *Repo: `react-intro`*                                                                         	|         [:15] Functional Components<sup>1</sup>; and Functional Components Exercise. -- *Repo: `react-es6-functional`*        	|                                [:30] Heroku. -- *Repo: `react-apis-heroku-declarative`* 	|                                               	|
| [:25] JSX<sup>1</sup>; and Virtual DOM<sup>1</sup> -- *Repo: `react-intro`*                                                                                     	|                            [:30] Component Lifecycle. -- *Repo: `react-es6-functional`*                           	|                                       [:15] *Optional*: Quiz 5. -- *Repo: `react-instructor-notes`* 	|                                               	|
| [:30] Props<sup>1</sup>; Multiple Props; and Multiple Props with Objects. -- *Repo: `react-intro`*                                                  	| [:10] Unidirectional Flow<sup>1</sup>. -- *Repo: `react-es6-functional`*                                                      	| [:30] Film Exercise 4 - APIs. -- *Repo: `react-apis-heroku-declarative`*     	|                                               	|
| [:30] Props Challenge (Blog project). -- *Repo: `react-intro`*                                                                          	| [:20] Immutable Data Types. -- *Repo: `react-es6-functional`*                                                     	| [1:00] ATM Lab. -- *Repo: `react-atm`*                                                  	|                                               	|
| [:30] Nested Components; and Nested Components Challenge (Blog project). -- *Repo: `react-intro`*                                       	| [:15] Section Summary and *Optional*: Quiz 3. -- *Repos: `react-es6-functional`; `react-instructor-notes`, respectively*      	| [1:00] Tic Tac Toe Exercise. -- *Repo: `react-tictac-toe`*                              	|                                               	|
| [:20] Section Recap; and LoTR Codealong / Exercise-- *Repo: `react-intro`*                                                              	| [:30] [Optional] Film exercise - unidirectional flow. -- *Repo: `react-es6-functional`*                           	| [:20] Documentation. -- *Repo: `react-documentation`*                                   	|                                               	|
| [:15] *Optional*: Quiz 1 -- *Repo: `react-instructor-notes`*                                                                            	| [:25] Router Introduction; Browser History Mechanics; Modern Browser History Mechanics. -- *Repo: `react-router`* 	| [:30] Documentation Group Exercise. -- *Repo: `react-documentation`*                    	|                                               	|
| [:20] *Optional*: Film Exercise - Components. -- *Repo: `react-intro`* -- **Note**: Quite tough. Recommended in class. Uses ES6.        	| [:25] Router intro<sup>1</sup>; all of dentist codealong. -- *Repo: `react-router`*                                           	|                                                                                         	|                                               	|
| [:30] State<sup>1</sup>; and State Exercise (Blog Project). -- *Repo: `react-state-exercises`*                                                      	| [:30] Router Blog Exercise. -- *Repo: `react-router`*                                                             	|                                                                                         	|                                               	|
| [:10] Component Lifecycle. -- *Repo: `react-state-exercises`*                                                                           	| [:10] *Optional*: Quiz 4 - Router. -- *Repo: `react-instructor-notes`*                                                        	|                                                                                         	|                                               	|
| [:30] ToDo Exercise. -- *Repo: `react-state-exercises`*                                                                                 	| [:15] APIs; Data Types; Fetch. -- *Repo: `react-apis-heroku-declarative`*                                         	|                                                                                         	|                                               	|
| [:10] Recap<sup>1</sup>. -- *Repo: `react-state-exercises`*. -- **Note**: After this, be sure students have an idea when and when not to use React. 	| [:15] Fetch Codealong. -- *Repo: `react-apis-heroku-declarative`*                                                 	|                                                                                         	|                                               	|
| [:30 or Homework] Calculator Exercise. -- *Repo: `react-state-exercises`*.                                                              	| [:30] API Project (Blog Project). -- *Repo: `react-apis-heroku-declarative`*                                      	|                                                                                         	|                                               	|
| [:15] *(EOD if calc is hw).* *Optional*: Quiz 2. -- *Repo: `react-instructor-notes`*                                                                	|                                                                                         	|                                                                                         	|                                               	|
| [Homework *Day 2 if calc is hw*]. *Optional* Film Exercise - State. *Repo: `react-state-exercises`*. Note: Uses ES6.                    	|                                                                                                                   	|                                                                                         	|                                               	|

## Optional Quizzes and Review Guides
- **Quizzes**:. There are optionally short, ten question quizzes after each repo. The quiz questions and links are in the `quizzes` folder.
  - These are not referenced in anything student facing and can optionally be assigned at your discretion.
  - **Note:** The review guides are linked at the end of the quizzes.
- **Review Guides**: There are optionally review guides for a student to quickly reference in the future. These are located in [the `react-review-guides` repo](../../../react-review-guides/).
  - These are not referenced in anything student facing and can optionally be shared at your discretion.

## Solution Locations
- Solutions to exercises are on branches within their respective repos.
- Solutions to the blog project that's built throughout the class are in branches in the [`react-blog-project` repo](../../../react-blog-project).
- Solutions to the film project that's built throughout the class are in branches in the [`react-film` repo](../../../react-film).

## Important Notes on the Film Exercise
- There is a film exercise that is built upon throughout the class.
  - Please note that this exercise has some advanced JavaScript and starts out using ES6 (`const`, `let`, and arrow functions) before ES6 is explained in Unit 3. 
    - It's recommended that you look through the solution branches and then make a decision on whether to introduce exercises 1 and 2 at the beginning of the course, or if you'd like to assign exercises 1-3 as homework on the second day (after ES6 is taught). 
  - Because it adds time to the class and is a bit complicated, it is generally recommended that each exercise is homework. However, dedicate time each morning to go over and explain the solution.
  - The film exercises are not referenced anywhere else in the class and can safely be ignored if you so choose.

## Options on ways to teach the React Module
Note: See the `Readme.md` in the `schedules` folder for links to the repos and definitions of activity types.
- **Option 1**: Teach it like a normal class, entirely in classroom.
  - Follow the schedule above.

- **Option 2**: Teach flipped classroom
  - This means assigning as much reading as possible for homework; all exercises and codealongs during the day.
  - For a schedule on teaching React flipped, follow the `flipped-classroom-schedule.md` in the `schedules` folder.
- **Option 3**: Teaching ES6 first, before React.
  - [ES6 is part of unit 3](../../../react-es6-functional/) - the `react-es6-functional` repo.
  - If you'd like to teach ES6 before you start React, you will teach lessons 1-6 of unit 3 before starting back at unit 1 for the rest of the React module
      - **Note**: `02-ES6-ConstLet.md` has a thought exercise near the end that refers to a blog students do in unit 2 and has JSX in it, so it might be confusing if you haven't started React first.
  - If the students already know ES6, you can skim over these lessons - lesson 6 has a helpful recap you might want to do.
  - **Note**: Units 1 and 2 do not use most standard ES6 (`const`, `let`, arrow functions) as it's not designed to be taught until unit 3, so you'll need to give your students a headsup that you went out of order (to avoid the question "Why is this all `var`?").
