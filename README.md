# Project: References vs Copying

## About
I've been doing some form of web development for about seven years or so... mostly basic HTML, CSS and JavaScript. I've taken two of [Udacity's](https://www.udacity.com) nanodegree programs: Front End and Full Stack Web Developer. I have learned a lot from those courses but I know that there are situations and use cases that I haven't seen or been exposed to.

I recently heard about Wes Bos and also his 30 Day JavaScript challenge. It's a free course (at least during the writing of this) and it can be found here: [javascript30.com](https://javascript30.com)

This project is a practice in writing vanilla JavaScript and to learn about other use cases.

### View Project
[Click here to view the live project.](https://junclemente.github.io/j30-references/)


#### Project takeaways
* Strings, numbers, and booleans can be copied to another variable. Changing the value of the variable will not change the value of the variable it was assigned to: 

```javascript
let var1 = 10;
let var2 = var1;
var1 = 100;
console.log(var1, var2);
// Expected output: 100 10
```

* Arrays, when assigned to another variable, creates a reference to the original array and therefore a change to the new array will affect the original array. This is also the same for objects:

```javascript
let array1 = ['Zero', 'One', 'Two', 'Three', 'Four'];
let array2 = array1;

array2[1] = '1';
console.log(array2);
// Expected output: ['Zero', '1', 'Two', 'Three', 'Four'];

console.log(array1);
// Expected output: ['Zero', '1', 'Two', 'Three', 'Four'];
// Change to array2 will be changed in array1.

const person = {
	name: 'John Cage',
	age: 80
};

const person2 = person;
person2.number = 99;
console.log(person.number)
// Expected output: 99
```

* How to create copies of arrays instead of references:

```javascript
// Use slice without any arguments
const newArray = array.slice();

// Create new array and concat old array
const newArray = [].concat(players);

// Use ES6 'spread' function
const newArray = [...array];
```

* How to create copies of objects instead of references:

```javascript
const person2 = Object.assign({}, person, { number:99});

const person3 = {...person};
``` 