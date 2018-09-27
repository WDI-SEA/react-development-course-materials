# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Imperative and Declarative Programming

## Learning Objectives:
*After this lesson, you will be able to:*
- Create a JavaScript function via declarative programming.
- Create a JavaScript function via imperative programming.
- Contrast imperative and declarative.

---

## Imperative and Declarative Programming

```
ask everyone in the room to line up
for every person in the line
  ask each person to come to the front of the room
  ask each person to then speak their name
```

<aside class="notes">

**Talking Points**:

- Imperative and declarative programming are two terms that you might encounter. Most developers begin by writing _imperative_ code. That is to say, most developers:
1. Outline what they need to do.
2. Write it out step-by-step.

- Writing pseudocode is an excellent example of writing things out step-by-step the imperative way. For example, if we asked everyone in the room to say their name, we could conceptually write it out as seen here.

</aside>

---

To explore the imperative way of thinking, let's open this CodePen: https://codepen.io/SuperTernary/pen/eEVVvg?editors=0010

- We could write that out in JavaScript by creating an array of those people.

```js
let room = ['Superman', 'Black Panther', 'Wonder Woman', 'Iron Man']
```

- Next, we could loop through them and assign each active speaker to a variable named _person_.

```js
let room = ['Superman', 'Black Panther', 'Wonder Woman', 'Iron Man']

for (let i = 0; i < room.length; i++) {
  let person = room[i]
}
```

- Finally, we have them speak their name; or in our case, we'll just _console.log()_ their name out as represented by the _person_ variable.

```js
let room = ['Superman', 'Black Panther', 'Wonder Woman', 'Iron Man']

for (let i = 0; i < room.length; i++) {
  let person = room[i]
  console.log("Imperative way: " + person)
}
```

<aside class="notes">

**Teaching Tips**:

- For convenience, Slack the CodePen URL to students: https://codepen.io/SuperTernary/pen/eEVVvg?editors=0010

**Talking Points**:

- Run this in CodePen and check the console tab. It works: We've built this function using the *imperative* way of thinking.

- We have explicitly listed out each step, paying attention to each and every detail of what we needed to achieve.
- Imperative programming focuses on the _why_, _how_, _where_, and _when_ your code executes. It allows precise control over your code and allows for line-by-line code execution; you're writing every single thing that happens.

</aside>

---

Now, let's break from this approach for just a moment. Below that function in CodePen (leave the array!), let's look at building something in the **declarative** manner.

Now, if we want to perform the same action, we could write our loop like so:

```js
room.forEach((person) => {
  console.log("Declarative way: " + person);
});
```


<aside class="notes">

**Talking Points**:

- Run it! It still lists the people in the room. Consider how much less code it took.

- What happened? Well, JavaScript has a built-in method that loops over arrays for you. `.forEach()` does the same thing as that `for` loop you wrote above... except you had to write a lot less.

- `forEach` is a method in declarative programming. Instead of writing every single step yourself (i.e., instead of explicitly writing the _why_, _how_, _where_, and _when_ of your program), this method only cares about *what* you want.

- Instead of taking the time to write out a specific set of instructions to receive a result, you focus on just one thing: the result. This might sound a little confusing at first, so open up CodePen and try solving the following problem.

- We have been employing declarative code this whole time. Map is an excellent example of doing things in a declarative way.

</aside>

---

## Practice: Applying a Discount to Items in a Shopping Cart

![tv show](./assets/saved-by-the-bell.jpg)

How was your discount coded? What would be the steps of an **imperative approach**?

<aside class="notes">

**Talking Points**:

- Here's a scenario for you: To your utter delight, your favorite vintage television series has just been released for purchase. After adding it to your shopping cart, you scour the internet for a discount code. Finally, you find one! You enter `TREATYOSELF2020` into your cart's coupon code input box, and instantaneously your cart reflects the discounted price. Success!

</aside>

---

## Practice: Applying a Discount to Items in a Shopping Cart (Continued)

An **imperative** approach might:
1. Declare an object consisting of the items in the cart with the original prices.
2. Loop through that object with a `for` loop, updating the price as it goes.

And this would be explicitly coded line-by-line, like this:

```js
// Imperative approach
// oh boy! Zelda games! On sale! I need them!
let items = [
  {
    title: 'Breath of the Wild',
    price: 49.99
  },
  {
    title: 'The Minish Cap',
    price: 29.99
  },
  {
    title: 'Twilight Princess',
    price: 49.99
  }
];

// calculate the discount of 50% off
let discountedItems = [];
// loop on through
for (let i = 0; i < items.length; i++) {
  // create a new item, update the sale price thanks to the coupon, and push into the discountedItems array
  discountedItems.push({
    title: items[i]['title'], // keep the title
    price: items[i]['price'] * 0.5  // update the price
  });
}
```

<aside class="notes">

**Talking Points**:

- The imperative approach to writing code gives us full control of *how* we add the updated price into the new array. In this case:
1. _When_ we create the object, we set the initial attributes.
2. We access attributes directly through indices that represent _which_ object and _what_ attribute we want to select.
3. _How_ we do this is by creating a new array and updating the values to push to the new object.

---

Add `console.log(items); console.log(discountedItems);`
and hit `run` in this CodePen:https://codepen.io/SuperTernary/pen/brLLRb?editors=0011

<aside class="notes">

**Teaching Tip**:

- For convenience, Slack the CodePen URL to students: https://codepen.io/SuperTernary/pen/brLLRb?editors=0011

**Talking Points**:

- Try it out!
- It works, right?

</aside>

---


```js
let discountedItems = items.map((item) => {
  return {
    title: item.title,
    price: item.price * 0.5
  }
})
```

<aside class="notes">

**Talking Points**:

- This is fairly clean code, but we could write more succinct code using a **declarative** style. We'll use the array's built-in `.map` method to accomplish the same thing. We'll focus on _what_ we want (just the updated values) and we'll let `.map` take care of the _how_.

- Try it! This goes right after the "items" array declaration, replacing all the calculation code (the `for` loop and the discountedItems array before that).

- Using the declarative approach, we declare that we intend to .map through an array and create a newly updated version of it.

- _"But what if that method breaks?"_ you might be thinking. While a problem, you would know exactly what is broken: the `.map` method (or, more likely, your syntax is incorrect). This allows for easy debugging and testing. Consider how you would debug the imperative version of the code instead. How would your approach differ?

---

## Wrapping It Up

Declarative and imperative are two different styles of writing code.

- Imperative is commonly found in object-oriented programming environments where you focus on a line-by-line execution path, working with objects.

With modern web development's focus on simplicity, some developers have been leveraging declarative techniques.
- React.js is one framework that uses a declarative approach. Vue.js is another. You'll find that many asynchronous JavaScript techniques rely on declarative programming techniques for ease of readability.

<aside class="notes">

**Talking Points**:

- Neither method is incorrect, but declarative code tends to lead to DRY, clean code. And a final fun fact: Functional programming is a subset of declarative programming. If you've ever used a functional language, such as Haskell or Lisp, or written calculus, you've likely written declarative code.

- This was a mini-lesson to get us thinking about different ways of programming.
- You will likely encounter both ways of writing code as you continue in your development path, and it is good to be aware of both!

</aside>

