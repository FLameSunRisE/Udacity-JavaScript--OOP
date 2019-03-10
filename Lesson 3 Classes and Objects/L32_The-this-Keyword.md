# The \`this\` Keyword {#header-title}

## `this`in Constructor Functions {#this-in-constructor-functions}

```js
function Cat(name) {
 this.name = name;
 this.sayName = function () {
   console.log(`Meow! My name is ${this.name}`);
 };
}

const bailey = new Cat('Bailey');
// bailey looks like this
//{
//  name: 'Bailey',
//  sayName: function () {
//  console.log(`Meow! My name is ${this.name}`);
//}
//}

bailey.sayName();
// 'Meow! My name is Bailey'
```

## When is`this`Assigned? {#when-is-this-assigned-}

```js
const dog = {
  bark: function () {
    console.log('Woof!');
  },
  barkTwice: function () {
    this.bark();
    this.bark();
  }
};

dog.bark();
// Woof!

dog.barkTwice();
// Woof!
// Woof!
```

### Question:![](/assets/L3_2Q1.png)

### Question2:

Consider the following constructor function,`City`:

```js
function City(name, population) {
  this.name = name;
  this.population = population;

  this.identify = function () {
    console.log(`${this.name}'s population is ${this.population}.`);
  };
}
```

The following is executed:

```js
const sanFrancisco = new City('San Francisco', 870000);
```

What is the value of`this`?

* Ans : The newly-created object, referenced by sanFrancisco
* Solution : Depending on how a function is invoked, the value of this is set to a different value.



