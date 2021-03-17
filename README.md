# Functional
This exercise is about using functional programming concepts in JavaScript. Common concepts in functional programming is
 that everything is stateless (no changes in variables) and consists of functions. Latest addition to Javascript was ES6
 which supports functional programming in JavaScript. In this exercise we will explore some of these concepts.

#### Recommended reading
- [An Absolute Beginner's Guide to Using npm](https://nodesource.com/blog/an-absolute-beginners-guide-to-using-npm/)

#### Useful resources
- [JSON](https://www.json.org/json-en.html)
- [Callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
- [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

#### Concepts
- Callback functions
- Arrow/Lambda functions
- Map, Reduce and Filter functions
- Javascript Object Notation (JSON)

## Goals
1. Introduction to functional programming:​ After doing this exercise we should be comfortable in using certain
functional programming functions such as map/filter/reduce.
2. Introduction to ES6 Javascript:​ After doing this exercise we should be familiar with basic usage of ES6 Javascript.
3. Introduction to an npm project: After this exercise we should be comfortable with setting up a basic npm based project-

### What to do?
This assignment is about working with data using functional programming concepts like callbacks. That means the exercises should
be solved using a functional approach (map/filter/reduce) instead of the imperative approach (for-loops).

You will create a nodejs CLI (Command Line Interface) app that will read in a JSON file `MOCK_DATA.json` and print some values. The JSON file consists of different person objects that have a first name, last name, email, gender, ip address and age.
 
### Setup
JavaScript uses npm for managing a project and its dependencies, this is similar to Gradle/Maven for Java.
Start by initializing a project (see [recommended reading](#recommended-reading)) via `npm` and install the following packages:
- [eslint](https://eslint.org/): JavaScript linter which checks your coding style.
- [jest](https://jestjs.io/): Testing framework, similar to JUnit but for JavaScript.

ESLint should be set up to use code style enforcing, CommonJS, no framework, no TypeScript, Node and the popular AirBnB style guide. It has a pretty strict rules to be enforced but you can always
change them in `.eslintrc.js`. **Tip:** It's a smart idea to take help from your teammates during setup, as it's very common to
run into issues that someone else has already encountered.
 
#### Exercise 1–8
> **Assistant's Note:** If you would like to do this in a TDD (Test driven development)
> manner, then start with the tests first! It is actually recommended by many!

Create a node CLI (Command Line Interface) app that reads in a JSON file of choice (with the same format as `MOCK_DATA.json`) and prints out the following:
1. The number of females
2. The first and last name of all people that are older than 35.
3. The total age of all people summed.

4. Average age of all people.
5. The first name and last name of males that are younger than 43 but older than 22 who starts their first name or last name with the letter L.
6. The first name and last name and ip adress of people that have government emails.<br/><br/>_**Note:** Government email addresses are the ones that contain the domain name `gov` in the **domain part of the email** (the part after the `@`). This one might be a bit tricky due to how a domain is identified. For example `aa@hello.gov.com` and `bb@world.gov` are valid government email address but `cc@web.govest.com` is not._

7. **Bonus (Optional)** The age (incremented by 10), name, ip address and year for everyone that has a first name that starts with letter 'k' and last name that ends with letter 's'. 
8. **Bonus (Optional)** The first name, last name, ip address and the birth date of everyone who is between the ages of 35 and 80 (inclusive) and with a last name starts with the letter D.<br/><br/>_**Note:** Since there is only an age in the json file it is impossible to tell exact birth date so feel free to make them up but they have to be randomized and still make sense. (i.e. if someone has age 55, their random birth date has to fall within the range that is logical given the date you run the application)_


#### Exercise 9
Write tests for at least 3 of the previous exercises using _jest_. Tests look a bit different in jest but they are quite easy,
here is how a sample jest test could look like (assuming your main file is `submission.js`:
```javascript
// submission.js
function femalesCount(listOfPeople) {
    ...
    return count;
}

module.exports = femalesCount; // This is needed so that we can import it in another file
                               // If you want to export several functions, put them all inside an object and export the object
```
```javascript
// submission.test.js
const femalesCount = require('../src/solution'); // Use the path to your submission file

test('femalesCount should count correct number of females', () => {
  expect(femalesCount([
    {
      id: 7, first_name: 'Minne', last_name: 'MacGilfoyle', email: 'mmacgilfoyle6@amazon.co.jp', gender: 'Female', ip_address: '12.246.212.112', age: 54,
    },
    {
      id: 8, first_name: 'Purcell', last_name: 'Mearns', email: 'pmearns7@chicagotribune.com', gender: 'Male', ip_address: '60.16.88.134', age: 24,
    },
    {
      id: 9, first_name: 'Amanda', last_name: 'Gownge', email: 'agownge8@t.co', gender: 'Female', ip_address: '246.160.41.135', age: 95,
    },
    {
      id: 10, first_name: 'Tybie', last_name: 'Tille', email: 'ttille9@cargocollective.com', gender: 'Female', ip_address: '82.56.248.7', age: 30,
    },
  ])).toBe(3);
});

```
Tests can then be run with the npm test command
```bash
npm test
```
> **Assistant's Note:**
> The test above uses a list with some sample people as an input and not the entire `MOCK_DATA.json` file. This makes it easier to get an overview of
> the test's actual input. This does however mean that the functionality must be divided into functions of higher cohesion
> .i.e one function reading the file and one function taking in the list and calculating the desired result.

###
