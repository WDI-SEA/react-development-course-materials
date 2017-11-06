# Instructors' Guide to teach the React Module

Note 1: The term "React Module" refers to all 8 React repos taught sequentially.

Note 2: No links open in a new tab. I don't know why - embedding HTML didn't work. If you can fix it, let me know.

Note 3: List of all repos is the `list-of-repos.md` in this folder.

[Here is a quick overview of the course](https://trello.com/invite/b/Ypm9Tsho/06c64ffa2be14b85a662e71ff10ac3e8/bitmaker-react-project) concepts and timings - not necessarily each file.

## Options on ways to teach the React Module
Note: See the `Readme.md` in the `schedules` folder for links to the repos and definitions of activity types.
- **Option 1**: Teach it like a normal class, entirely in classroom.
  - 5 days.
  - See `normal-schedule.md` in the `schedules` folder for an outline with timings.
- **Option 2**: Teach flipped classroom
  - This means assigning as much reading as possible for homework; all exercises and codealongs during the day.
  - For a schedule on teaching React flipped, follow the `flipped-classroom-schedule.md` in the `schedules` folder.
- **Option 3**: Teaching ES6 first, before React.
  - [ES6 is part of unit 3](../../../react-es6-functional/) - the `react-es6-functional` repo.
  - If you'd like to teach ES6 before you start React, you will teach lessons 1-6 of unit 3 before starting back at unit 1 for the rest of the React module
      - **Note**: `02-ES6-ConstLet.md` has a thought exercise near the end that refers to a blog students do in unit 2 and has JSX in it, so it might be confusing if you haven't started React first.
  - If the students already know ES6, you can skim over these lessons - lesson 6 has a helpful recap you might want to do.
  - **Note**: Units 1 and 2 do not use most standard ES6 (`const`, `let`, arrow functions) as it's not designed to be taught until unit 3, so you'll need to give your students a headsup that you went out of order (to avoid the question "Why is this all `var`?").

## Optional Quizzes and Review Guides
- **Quizzes**:. There are optionally short, ten question quizzes after each repo. These are linked in the `normal-schedule.md` and `flipped-classroom-schedule.md`. The quiz questions and links are in the `quizzes` folder.
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
  - The solutions to the various prompts are in branches.
  - Please note that this exercise has some advanced JavaScript and starts out using ES6 (`const`, `let`, and arrow functions) before ES6 is explained in Unit 3. It's recommended that you look through the solution branches and then make a decision on whether to include the film exercise throughout the course or whether to have it be an additional recap project near the end (all at once, after the Heroku lecture).
  - Because it adds time to the class and is a bit complicated, it is generally recommended that each exercise is homework. However, dedicate time each morning to go over and explain the solution.
  - The film exercises are not referenced anywhere else in the class and can safely be ignored if you so choose.
