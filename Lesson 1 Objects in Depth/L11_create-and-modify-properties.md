## Creating Objects {#creating-objects}

```js
// Using literal notation:
const myObject = {};

// Using the Object() constructor function:
const myObject = newObject();
```

## Modifying Properties {#modifying-properties}

* cat object

```js
const cat = {
  age: 2,
  name: 'Bailey',
  meow: function () {
    console.log('Meow!');
  },
  greet: function (name) {
    console.log(`Hello ${name}`);
  }
};
```

* change a little bit

```js
at.age += 1;

cat.age;
// 3

cat.name = 'Bambi';
cat.name;
// 'Bambi'
```

* after change : cats

```js
{
  age: 3,
  name: 'Bambi',
  meow: function () {
    console.log('Meow!');
  },
  greet: function (name) {
    console.log(`Hello ${name}`);
  }
};
```

## Adding Properties {#adding-properties}

```js
const printer = {};

printer.on = true;
printer.mode = 'black and white';
printer['remainingSheets'] = 168;
printer.print = function () {
  console.log('The printer is printing!');
};
```

* printer looks like this:

```js
{
  on: true,
  mode: 'black and white',
  remainingSheets: 168,
  print: function () {
    console.log('The printer is printing!');
  }
}
```

## Removing Properties {#removing-properties}

```js
delete printer.mode;
// true
printer.mode;
// undefined
```

## Question :

### Q1:

![](/assets/L1Q1.png)

### Q2:

Consider the following`house`object:

```js
let house = {
  color: 'green',
  numRooms: 4,
  numWindows: 8,
  forSale: false
};
```

Write an expression to delete the`numWindows`property from`house`.

* Ans: delete house.numWindows;
* Notes : The`delete`operator removes a property from an object, and returns a boolean indicating successful deletion. CONTINUE

### Q3:

Consider the updated house object from above:

```js
let house = {
  color: 'green',
  numRooms: 4,
  forSale: false
};
```

Write an expression to add a new hasGarage property to house. Set the value of the hasGarage property to true.

* Ans: house.hasGarage = true;
* Notes:

```js
//Here are two possible solutions:
house.hasGarage = true;
house['hasGarage']= true;
```

## Comparing an Object with Another Object {#comparing-an-object-with-another-object}

```js
const parrot = {
  group: 'bird',
  feathers: true,
  chirp: function () {
    console.log('Chirp chirp!');
  }
};

const pigeon = {
  group: 'bird',
  feathers: true,
  chirp: function () {
    console.log('Chirp chirp!');
  }
};

parrot === pigeon;
// false

const myBird = parrot;
myBird === parrot;
// true

myBird === pigeon;
// false
```

### Q4:![](/assets/L1_2Q4.png)

* Notes : Primitives \(e.g. numbers, strings, booleans, etc.\) are immutable values.

### Q5:

Consider the following:

```js
let string = 'orange';

function changeToApple(string) {
  string = 'apple';
}

changeToApple(string);

console.log(string);
// ???
```

What is logged to the console?

* Ans : orange
* Solution:  Within changeToApple\(\), string is assigned to 'apple'. However, this change is only relevant within the function; outside, the value of string remains 'orange'.

### Q6:

Consider the following object,`oven`:

```
const oven = {
  type: 'clay',
  temperature: 400
};
```

What is the value of`oven`'s`temperature`property after the following operations?

```
const newOven = oven;
newOven.temperature += 50;
```

* Ans: 450 
* Solution: Because newOven and oven refer to the same object, increasing the value of newOven's temperature property by 50 also increasing that of oven's.



