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



