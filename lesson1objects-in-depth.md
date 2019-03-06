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



