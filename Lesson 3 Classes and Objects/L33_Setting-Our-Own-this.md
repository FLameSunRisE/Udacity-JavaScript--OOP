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

```
function multiply(n1, n2) {
  return n1 * n2;
}

multiply.call(window, 3, 4);
// 12
multiply.apply(window, [3, 4]);
// 12

```



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



