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

## What Does`this`Get Set To? {#what-does-this-get-set-to-}

| Call Style | 'new' | method | function |
| :--- | :--- | :--- | :--- |
| this | {} | object itself | global object |
| Example | new Cat\(\) | bailey.sayName\(\) | introduce\(\) |

### Question3:

Consider the following object,`building`:

```js
const building = {
  floors: 5,
  addFloor: function () {
    this.floors += 1;
  }
};

building.addFloor();
// ???
```

What is the value of`this`when`building.addFloor();`is executed?

* Ans: building
* Solution : 
  Recall that a method can directly access the object on which it was called. In this case, it modifies `building `'s `floors `property by incrementing its value by 1.



