---
title: What is Jest
image: 3.gif
description: The Wonders of TDD
---

[Jest](https://jestjs.io/) is a popular test framework for JavaScript that allows developers to build unit tests, work with custom matchers, create mocks, and check snapshots of visual components in a simple and accessible manner. It is a testing framework based on [Jasmine](https://jasmine.github.io/), providing an assert library, a test runner, and support for various testing functionalities. Although originally developed in the context of [React](https://reactjs.org/), Jest is a versatile testing framework that can be used in any JavaScript project.

<!-- ![image alt text](http://blog.302chanwoo.com/wp-content/uploads/2017/12/302chanwoo_flower_main.jpg)
![Imgur](https://i.imgur.com/uSZrE6I.gif)

[![image alt text](https://content.codecademy.com/courses/learn-cpp/community-challenge/highfive.gif)](https://content.codecademy.com/courses/learn-cpp/community-challenge/highfive.gif) -->

## Who created Jest

Jest was developed by the Facebook team and, while it originated in the React ecosystem, it has evolved into a general-purpose testing framework that can be utilized in various situations. Once developers start using Jest, they often find it to be a powerful and valuable resource, making it their preferred choice for testing.

## Why Jest

During a volunteering experience in the Equity Cohort program, I had the opportunity to learn and become familiar with Jest. Before that, I had not extensively tested my code (unless we count Codewars or Leetcode challenges), and I found the process to be more intricate than I had initially thought. However, using Jest provided me with a new perspective on software development. It instilled a more cautious mindset, emphasizing the importance of testing to ensure code meets expectations and adheres to desired standards. Properly testing code is a crucial strategy for minimizing the possibility of errors in production that could potentially break the application or compromise product quality.

In the fast-paced tech industry, where accelerated deadlines are common, users can be unforgiving of mistakes. Therefore, while writing unit tests might seem like a time-consuming task, it actually facilitates maintenance and guarantees that your code behaves as expected in the long run.

## Test-Driven Development (TDD) with Jest

Test-Driven Development (TDD) is a software development approach that emphasizes writing tests before writing the actual code. In TDD, developers first create test cases that define the desired behavior of the code. These tests initially fail since the code implementation is yet to be written. The developer then writes the code to make these tests pass, ensuring that the code meets the specified requirements. The process is iterative, with developers continuously writing tests, implementing code, and running tests to achieve the desired functionality.
If you want to dive deeper into the sea of TDD here's a good article on it [What is Test Driven Development](https://www.guru99.com/test-driven-development.html)

![code](https://i.imgur.com/rxVGFYk.png)

## If you are still not convinced, here are 4 reasons why testing is essential

1. **Unit Testing Saves Time...and Money**: By writing unit tests, you can identify potential bugs early and fix them immediately, avoiding more complex issues later in the development process.

2. **Your Code is More Reliable and Reusable**: Dividing your code into smaller units or components, each with specific responsibilities, increases its reliability and reusability. Additionally, having already written tests makes it easier to reuse the code in different projects.

3. **Good Unit Tests Serve as Documentation**: Well-written unit tests effectively document the intended behavior of your code, making it easier for other developers to understand and collaborate on the project.

4. **Unit Tests Improve Teamwork**: By sharing and reviewing each other's code, the team can better understand the logic behind the code, leading to more efficient collaboration and agile development.

Writing long code without errors can be a pleasant experience, but it doesn't always happen. There's a saying that there are no programs written without errors. So, let's consider a real-life example that might give you a better idea of why Jest is a valuable resource:

#### "Have I considered all the variables and/or error states if some information is not gathered properly?"

These types of questions can cover a broad spectrum, and they are essential to ensure the reliability and robustness of your code. Now let's explore four definitions in testing that can help us understand this better:

- **Anomaly**: It is a behavior that is not expected within the system.
- **Defect**: A situation that can be reproduced and is known to cause system problems.
- **Failure**: System inability within known margins.
- **Error**: Human action that generates damage to the system.

We can apply these definitions to the following questions for our example function `isUpperCase`:

- What happens if you pass a word in uppercase?
- What happens if you pass a lowercase word to it?
- What happens if you pass it a mixed word (upper and lower case)?
- What happens if you pass it a number instead of a string?
- What happens if you pass it a boolean instead of a string?
  <br>

## Testing Failures

Rather than just testing the ideal scenarios, it's better to build tests that try to break your functions. By testing various unexpected inputs and edge cases, you can discover potential bugs and vulnerabilities early in the development process.

# Now, Let's Dive into Example Code

## How to Structure and Write Tests for Your Function

Before we proceed with the example, make sure you have [Node.js](https://nodejs.org/en/download/) installed. Next, you can add Jest to your project by running the following command in your terminal:

```bash
npm install --save-dev jest
```

After installing Jest, update the `scripts` section in your `package.json` as follows:

```json
"scripts": {
    "test": "jest"
}
```

Now, let's look at an example using the classic FizzBuzz problem, which is often given in coding interviews.

### Our Function: fizzbuzz.js

# ![code](https://i.imgur.com/xvK1m5y.png)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Code</summary>
  <pre style="padding: 2em 2em ">
  <samp >
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
</samp></pre>
</details>
<br>
## We’ll explain Jest’s syntax in more detail later. For now, understand that we’re verifying that
<br>

- Passing 1 should return the number 1.
- Passing 7 should return the number 7.
- Passing a number divisible by 3 should result in "Fizz".
- Passing a number divisible by 5 should result in "Buzz".
- Passing a number divisible by both 3 and 5 should result in "FizzBuzz".

<br>

### Our Test: fizzbuzz.test.js

This is what your test file should look like. Note that the file name should contain the word "test" to follow Jest's naming convention for test files. In this file, we will conduct experiments and ensure our code functions correctly.

# ![code](https://i.imgur.com/CF4USwT.png)

 <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Code</summary>
  <pre style="padding: 2em 2em ">
  <samp >
const fizzbuzz = require("./fizzbuzz");
describe("FizzBuzz Test", () => {
  test("returns 1 for the number 1", () => {
    expect(fizzbuzz(1)).toEqual(1);
  });
  test("returns 7 for the number 7", () => {
    expect(fizzbuzz(7)).toEqual(7);
  });
  test('returns "Fizz" for the number 3', () => {
    expect(fizzbuzz(3)).toEqual("Fizz");
  });
  test('returns "Buzz" for the number 5', () => {
    expect(fizzbuzz(5)).toEqual("Buzz");
  });
  test('returns "FizzBuzz" for the number 15', () => {
    expect(fizzbuzz(15)).toEqual("FizzBuzz");
  });
});
</samp></pre>
</details>
<br>

### Running the Test

You are now ready to run your first test! In your terminal, simply run the following command:

```bash
npm test
```

You should see the following result:

# ![code](https://i.imgur.com/eEUEgps.png)

   <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Code</summary>
  <pre style="padding: 2em 2em ">
  <samp >
√ returns 1 for the number 1 (2 ms)
√ returns 7 for the number 7
√ returns "Fizz" for the number 3 (1 ms)
√ returns "Buzz" for the number 5
√ returns "FizzBuzz" for the number 15
Test Suites: 1 passed,
 1 total
Tests: 5 passed, 5 total
Snapshots: 0 total
Time: 0.479 s
Ran all test suites.
</samp></pre>
</details>
<br>

### Analyzing Test Coverage

To check what parts of the code are tested and ensure code coverage, we can make a small change to the `scripts` section in `package.json` as follows:

```json
"scripts": {
    "test": "jest --coverage"
}
```

This change prompts Jest to verify every line and provides a detailed coverage report. After running `npm test` again, you should see additional information like this:

```
-------------|---------|----------|---------|---------|-------------------
File         | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s
-------------|---------|----------|---------|---------|-------------------
All files    |     100 |      100 |     100 |     100 |
 fizzbuzz.js |     100 |      100 |     100 |     100 |
-------------|---------|----------|---------|---------|-------------------
```

Additionally, a folder containing multiple files, including an index.html file, will be created, providing a comprehensive breakdown of the code coverage.

With Jest, you can ensure that your code is thoroughly tested, making your applications more robust and reliable, which ultimately leads to better software development. Happy testing!

## Conclusion

In conclusion, Jest proves to be a powerful and popular test framework for JavaScript, offering developers a comprehensive testing solution with its simplicity and accessibility. It excels in writing unit tests, working with custom matchers, creating mocks, and checking snapshots of visual components. Developed by the Facebook team, Jest's versatility extends beyond React applications, making it a valuable asset for testing various JavaScript frameworks and projects.

From my experience with Jest during volunteering work, I gained a profound appreciation for the role of testing in software development. Writing unit tests not only detects potential bugs early but also enhances code reliability and reusability. Good unit tests serve as living documentation, clearly defining code expectations, while also promoting better teamwork by fostering code comprehension and collaboration.

Jest empowers developers to consider different scenarios and error states, encompassing anomalies, defects, failures, and errors. By running comprehensive tests, you can ensure all variables are accounted for and identify unexpected behaviors.

Thanks to Jest's straightforward syntax and easy integration with Node.js projects, setting up and running tests is seamless. Additionally, Jest's code coverage analysis highlights the tested parts of the codebase, providing valuable insights into the effectiveness of your tests.

To sum it up, Jest is an indispensable tool for modern software development. Embracing a testing-centric approach leads to improved code quality, easier maintenance, and increased team productivity. By incorporating Jest, you lay a strong foundation for creating reliable, efficient, and high-quality applications that exceed user expectations. So, in your coding endeavors, consider Jest to unlock the wonders of robust testing and propel your projects to new heights. Happy testing! 🚀

![Sonny and Mariel high fiving.](https://content.codecademy.com/courses/learn-cpp/community-challenge/highfive.gif)
