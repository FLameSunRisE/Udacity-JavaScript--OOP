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



