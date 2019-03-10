### call\(\) {#call-}

```js
function multiply(n1, n2) {
  return n1 * n2;
}

multiply(3, 4);
// 12
multiply.call(window, 3, 4);
// 12


const mockingbird = {
  title: 'To Kill a Mockingbird',
  describe: function () {
    console.log(`${this.title} is a classic novel`);
  }
};

mockingbird.describe();
// 'To Kill a Mockingbird is a classic novel'
```

* mockingbird.describe.call\(pride\);
  * First, the call\(\) method is invoked onto mockingbird.describe \(which points to a function\).
  * the value of this is passed into the call\(\) method: pride

```
const pride = {
title: 'Pride and Prejudice'
};
mockingbird.describe.call(pride);
// 'Pride and Prejudice is a classic novel'
```

### apply\(\) {#apply-}

Just like call\(\), the apply\(\) method is called on a function to not only invoke that function, but also to associate with it a specific value of this.

```js
function multiply(n1, n2) {
  return n1 * n2;
}

multiply.call(window, 3, 4);
// 12
multiply.apply(window, [3, 4]);
// 12
```

apply\(\) vs call\(\)

* call\(\):
   may be limited if you don't know ahead of time the number of arguments that the function needs
* apply\(\) :
   would be a better option, since it simply takes an array of arguments, then unpacks them to pass along to the function. Keep in mind that the unpacking comes at a minor performance cost, but it shouldn't be much of an issue.

```js
const mockingbird = {
  title: 'To Kill a Mockingbird',
  describe: function () {
    console.log(`${this.title} is a classic novel`);
  }
};


const pride = {
  title: 'Pride and Prejudice'
};

mockingbird.describe.call(pride);
// 'Pride and Prejudice is a classic novel'
mockingbird.describe.apply(pride);
// 'Pride and Prejudice is a classic novel'
```

### QUESTION 1 OF 5

Consider the following`dave`object, and the`sayHello()`function:

```js
const dave = {
  name: 'Dave'
};

function sayHello(message) {
  console.log(`${message}, ${this.name}. You're looking well today.`);
}
```

Let's say you want the message`'Hello, Dave. You're looking well today.'`printed to the console.

Which of the following expressions could you write to accomplish that?

* Ans:sayHello.apply\(dave, \['Hello'\]\);

### QUESTION 2 OF 5

Consider the following`Andrew`and`Richard`objects:

```js
const Andrew = {
  name: 'Andrew',
  introduce: function () {
    console.log(`Hi, my name is ${this.name}!`);
  }
};
```

```js
const Richard = {
  name: 'Richard',
  introduce: function () {
    console.log(`Hello there! I'm ${this.name}.`);
  }
};
```

When`Richard.introduce.call(Andrew);`is executed, what is logged to the console?

* Ans : 'Hello ther! I'm Andrew'

Consider the following:

```js
const andrew = {
  name: 'Andrew'
};

function introduce(language) {
  console.log(`I'm ${this.name} and my favorite programming language is ${language}.`);
}
```

Write an expression that uses the`call()`method to produce the message:`'I'm Andrew and my favorite programming language is JavaScript.'`

Ans : introduce.call\(andrew, 'JavaScript'\);

## Callbacks and`this` {#callbacks-and-this}

```js
function invokeTwice(cb) {
   cb();
   cb();
}

const dog = {
  age: 5,
  growOneYear: function () {
    this.age += 1;
  }
};

dog.growOneYear();
// (this works as expected)

dog.age;
// 6

invokeTwice(dog.growOneYear);
// undefined

dog.age;
// 6
```

## Saving`this`with bind\(\) {#saving-this-with-bind-}

* bind\(\) returns a new function that, when called, has this set to the value we give it.

```js
function invokeTwice(cb) {
   cb();
   cb();
}

const dog = {
  age: 5,
  growOneYear: function () {
    this.age += 1;
  }
};

const myGrow = dog.growOneYear.bind(dog);

dog.age;
// 7
```

![](/assets/L3_3Q4.png)



Consider the following:

```js
function invokeTwice(cb) {
   cb();
   cb();
}

const dog = {
  age: 5,
  growOneYear: function () {
    this.age += 1;
  }
};

const myGrow = dog.growOneYear.bind(dog);

dog.age;
// 7
```

Write an expression using`bind()`that allows us to "borrow" the`displayName()`method from`driver`for the`car`object to use. Note: The_expression itself_is sufficient \(no need to save it to a variable\).

  


