---
title: What is Jest
image: 3.gif
description: The Wonder of jest
---

**[Jest](https://jestjs.io/), is a popular test framework for JavaScript.**  With jest we can build unit tests working with custom matchers, create mocks or check snapshots of visual components as something simple and accessible. Jest which, based on [Jasmine](https://jasmine.github.io/), is not just a library, it is a testing framework. It means that it comes with an assert library, a test runner, and support for stuff. Since it has been specifically designed for testing React applications, it can also be used in other JavaScript frameworks.

# Who created jest

Jest has been developed by the Facebook team and, although it was born in the context of [React](https://reactjs.org/) , it is a general testing framework that we can use in any situation. Once you start with Jest, you won't want to change anymore.

# Why Jest

While volunteering for the Equity Cohort program, I got the opportunity to learn and become familiar with jest. Before the whole endeavor, I had not honestly tested my code in such a way 😅( unless we count Codewars or Leetcode ), and for me, it wasn't as simple as I would have thought. It gave me a new perspective on the process of software development. It ingrained a more cautious mindset for ensuring my applications reach a better structure because testing *ensures* that the code meets certain expectations and follows the standard we want to uphold. Testing our code is the best strategy we can implement to minimize the possibility of errors in production that may break your *app* or decrease the quality of the product.

In the *Tech* industry, it is widespread to deal with accelerated *deadlines* , where things must be implemented as soon as possible, and users can harshly punish mistakes. Therefore, although it may seem that doing unit tests “takes time,” the truth is that in the long term, it facilitates maintenance and guarantees that your code is doing what you expect it to do.

### If you are still not convinced, these are 4 reasons to *test* :

- **Unit Testing Saves Time...and Money** By writing unit tests you can identify many potential bugs and fix them immediately, instead of fixing them at different stages of your product.
- **Your code is more reliable and reusable** When your code is divided into units or components where each one has its responsibility or function, your code becomes more reliable and gives you more security and since you have already done tests you can reuse it: it is clean and efficient and you can migrate your code and tests to a new project.
- Good unit tests serve as **documentation and define** what your code is supposed to do.
- **Unit tests improve teamwork** . They will be able to follow the logic behind your code and your team will be able to coordinate their code accordingly. By reviewing each other's codes, teamwork is more agile.

Writing long code without errors is quite pleasant. But unfortunately this does not always happen. There is even a joke that there are no programs written without errors. So to set a real life example I propose to you the next question, It's one I had to consider when doing my volunteering work. It should a more give a solid idea as to why jest is a such valuable resource.

#### "Have I considered all the variables and/or error states if some information is not gathered properly?"

##### These types of questions can range from a very broad spectrum which would be a bit difficult to breakdown such as:

- If my project has user profiles, have I considered what it will look like the first time it's used, after information has been added?
- Are the mechanisms for editing information abundantly clear or is there room for improvement?

### But how do I go about "thinking of" and "answering" for such variables. 🤔

##### So a more simple approach is in order. There are 4 definitions in the tests that can help us better understand this and there will also be some demos after that can help us visualize it.

**Anomaly:** it is a behavior that is not expected within the system.

**Defect:** A situation that can be reproduced and is known to cause system problems.

**Failure:** System inability within known margins.

**Error** : human action that generates damage to the system.

#### We can try those out with the next few questions. In this case a way to ensure that your function is for example, `isUpperCase` works, is to test all possible inputs:

1.  What happens if you pass a word in uppercase?
2.  What happens if you pass a lowercase word to it?
3.  What happens if you pass it a mixed word (upper and lower case)?
4.  What happens if you pass it a number instead of a string?
5.  What happens if you pass it a boolean instead of a string?

#### Testing failures

It's better to find all the bugs now than later (in production), that's why you have to build your tests trying to **break your functions** . Instead of testing the ideal scenario, try to think of possible strange inputs that you could pass to your function.

# Now onto example code!

### How to structure and write the test for your function

#### Also in case you want to run the test yourself you will have to have had installed [nodejs](https://nodejs.org/en/download/) and then you can install [jest ](https://jestjs.io/)into your project by typing the following in your terminal :

```
npm install --save-dev jest
```

#### After that you update the the script section of the ` package.json` to the following

```
"scripts": {
    "test": "jest"
  }
```

### Our function: fizzbuzz.js

Here we have the classic FizzBuzz problem a test often given in coding interviews.

```js
function fizzBuzz(number) {
  if (number % 3 == 0 && number % 5 == 0) {
    return "FizzBuzz";
  } else if (number % 3 == 0) {
    return "Fizz";
  } else if (number % 5 == 0) {
    return "Buzz";
  } else {
    return number;
  }
}

module.exports = fizzBuzz;
```

## We’ll explain Jest’s syntax in more detail later. For now, understand we’re verifying that:

- passing 1 should return the number 1
- passing 7 should return the number 7
- passing an array containing 3 should result in “Fizz”
- passing an array containing 9 should result in “Fizz”
- an array containing 5 should result in “Buzz”
- an array containing 10 should result in “Buzz”
- an array containing 15 or 30 should result in “Fizzbuzz”

## Our test: fizzbuzz.test.js

This is what will go into your test file, notice that it has test in the name, that's intended and it is the proper syntax for how you name your test files. In this file is where we will be making all the experiments and finding out just how far our code can go 😎

```js
const fizzbuzz = require("./fizzbuzz");

describe("Here is where your overall description for the test goes"), () => {
  test("returns 1 for the number 1", () => {
    expect(fizzbuzz(1)).toEqual(1);
  });

  test("returns 7 for the number 7", () => {
    expect(fizzbuzz(7)).toEqual(7);
  });

  test('returns "Fizz" for the number 3', () => {
    expect(fizzbuzz(3)).toEqual("Fizz");
  });

  test('returns "Fizz" for the number 9', () => {
    expect(fizzbuzz(9)).toEqual("Fizz");
  });

  test('returns "Buzz" for the number 5', () => {
    expect(fizzbuzz(5)).toEqual("Buzz");
  });

  test('returns "Buzz" for the number 10', () => {
    expect(fizzbuzz(10)).toEqual("Buzz");
  });

  test('returns "FizzBuzz" for the number 15', () => {
    expect(fizzbuzz(15)).toEqual("FizzBuzz");
  });

  test('returns "FizzBuzz" for the number 30', () => {
    expect(fizzbuzz(30)).toEqual("FizzBuzz");
  });
});

```

### Running the test

We're now ready to run your first test. Back to your terminal, simply run **npm test**. Then this should be the result:

```
 √ returns 1 for the number 1 (2 ms)
    √ returns 7 for the number 7
    √ returns "Fizz" for the number 3 (1 ms)
    √ returns "Fizz" for the number 9
    √ returns "Buzz" for the number 5
    √ returns "Buzz" for the number 10 (1 ms)
    √ returns "FizzBuzz" for the number 15
    √ returns "FizzBuzz" for the number 30 (1 ms)

Test Suites: 1 passed, 1 total
Tests:       8 passed, 8 total
Snapshots:   0 total
Time:        0.479 s
Ran all test suites.
```

### Awesome! We passed all the test we set up but after all that, this question could pop into your head of "How do I know what parts of the code are tested if there are many different sets of files?"

We would have to go back to our `package.json` and update the scripts section again to answer that, thankfully its not much.

```
"scripts": {
    "test": "jest --coverage"
  }
```

That change makes jest verify every line plus much more and make sure that our code is 100% tested, then this should be what you see in addition to your previous information:

```
-------------|---------|----------|---------|---------|-------------------
File         | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s
-------------|---------|----------|---------|---------|-------------------
All files    |     100 |      100 |     100 |     100 |
 fizzbuzz.js |     100 |      100 |     100 |     100 |
-------------|---------|----------|---------|---------|-------------------
```

The change we made in addition to the above, it also creates a folder containing many files but more importantly an index.html file with a nice breakdown of everything.
