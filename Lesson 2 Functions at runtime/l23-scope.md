## Scope {#scope}

A function's runtime scope describes the variables available for use inside a given function. The code inside a function has access to:

1. The function's arguments.
2. Local variables declared within the function.
3. Variables from its parent function's scope.
4. Global variables.

![](/assets/L2_3_Scope.png)

```js
const myName = 'Jay';
// Global variable

function introduceMyself() {

  const you = 'student';
  // Variable declared where introduce() is defined
  // (i.e., within introduce()'s parent function, introduceMyself())

  function introduce() {
    console.log(`Hello, ${you}, I'm ${myName}!`);
  }

  return introduce();
}

//output
//Hello, student, I'm Jay!
```



### Q1:

![](/assets/L2_3Q1.png)



## JavaScript is Function-Scoped {#javascript-is-function-scoped}

```js
var globalNumber = 5;

function globalIncrementer() {
  const localNumber = 10;

  globalNumber += 1;
  return globalNumber;
}

console.log(globalIncrementer());
// 6

console.log(globalIncrementer());
// 7

console.log(globalIncrementer());
// 8

console.log(localNumber);

// ReferenceError: localNumber is not defined
```

> Block-Scoping 💡
>
> ES6 syntax allows for additional scope while declaring variables with the`let`and`const`keywords. These keywords are used to declare_block-scoped_variables in JavaScript, and largely replace the need for`var`.



## Scope Chain

![](/assets/L2_3Chain.png)

## Variable Shadowing {#variable-shadowing}



```
const symbol = '¥';

function displayPrice(price) {
  const symbol = '$';
  console.log(symbol + price);
}

displayPrice('80');
// '$80'
```

In the above snippet, note that`symbol`is declared in two places:

1. Outside the`displayPrice()`function, as a_global_variable.
2. Inside the`displayPrice()`function, as a_local_variable.

### Q3:

```
let n = 8;

function functionOne() {
  let n = 9;

  function functionTwo() {
    let n = 10;
    console.log(n);  // First log
  }

  functionTwo();

  console.log(n);  // Second log
}

functionOne();

console.log(n);  // Third log
```

Output ?

* Ans : 10,9,8



