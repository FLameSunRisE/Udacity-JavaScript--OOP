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



