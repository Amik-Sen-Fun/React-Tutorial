## ES6 important concepts

### Let vs var vs const

- var : The variable defined here it's scope is the function where it is defined. 

- let : The variable defined here is only accessible in the block defined. Preferred. 

- const : It is used to define constant value. It's scope is also blocked defined.

### Objects

```js
const person = {
	name: 'Mosh',
	walk: function(){}, 
	talk(){}, // ES6 method
};

// How to access?
person.talk(); // used when we know before hand what to access
person['name'] = 'John'; // used for dynamic variable access by storing 'name' in a variable
```

### `this` keyword

this returns a reference to an object where it is defined.

In case of stand alone function it returns the reference to the window object. But since strict mode is `on`, the window object is not returned and it shows undefined. 

### How to bind `this`?

functions in js are objects. So they have certain properties. One such method is bind and to bind an object we do. 

```js
const person = {
        name: 'Mosh',
        walk: function(){},
        talk(){}, // ES6 method
};

const walk = person.walk.bind(person);
walk(); // prints the person object
```
### Arrow Function

Compact way of writing functions. Say we have a list of jobs and we want to get the Active jobs. Say the list be : 

`const jobs = [
	{ id: 1, isActive: true},
	{ id: 2, isActive: true},
	{ id: 3, isActive: false},
]`

The traditional way to write this is: 

`const activeJobs = jobs.filter(function(job){ return job.isActive;});`

> filter() : takes in a predicate function

Analogous arrow function is 

`const activeJobs = jobs.filter(job=> job.isActive);`

> This is correct for only one parameter and one line function.

### The map method 

```js
const colors = ['red', 'green', 'blue'];

const items = colors.map(color => '<l1>' + color + '</l1>');

const items = colors.map(color => '<l1>${color}</l1>');
```

### Object Destructing 

```js
const address = {
	street: '',
	city:'',
	country: ''
};

const {street, city, country} = address;

const {street : st} = address; // renames street as st and takes street value of address
```

### Spread Operator

- Merging Array

```js
const first = [1,2,3];
const second = [4,5,6];

const clone = [...first, 'a', ...second];
const combined = first.concat(second);
```

- Merging objects

```js
const first = {name: 'Mosh'};
const second = {job: 'Instructor'};
const combined = {...first, ...second, location: 'Australia'};
```

### Classes
 To increase usability of code we write classes in JS. They are defined as:

```js
class Person{
	constructor(name){
		this.name = name;
	}
	walk(){
		console.log("walk");
	}
}

// defining a class object
const person = new Person("Amik");
```

### Inheritance


### Modules
