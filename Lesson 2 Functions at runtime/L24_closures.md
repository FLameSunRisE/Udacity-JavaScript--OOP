## closure {#functions-retain-their-scope}

* This process of a function retaining access to its scope

  * The function itself

  * The code \(but more importantly, the _scope chain of_\) where the function is declared

MDN defines a closure as:

> "the combination of a function and the lexical environment within which that function was declared."

```js
function myCounter(){
    let count = 0;
    return function(){
        count += 1;
        return count;
    };
}

let counter = myCounter();
counter.count;
// undefined
count;
//error: Uncaught ReferenceError:count is not defined
```

## Creating a Closure {#creating-a-closure}

```js
const myName = 'Andrew';

function introduceMyself() {
  const you = 'student';

  function introduce() {
    console.log(`Hello, ${you}, I'm ${myName}!`);
  }

  return introduce();
}

introduceMyself();
// 'Hello, student, I'm Andrew!'
```

### Q1:What is the output when`result(10);`is executed?

```js
function outerFunction() {
  let num1 = 5;

  return function(num2) {
    console.log(num1 + num2);
  };
}

let result = outerFunction();

result(10);
// ???
```

* Ans: 15

### Q2:

```js
/*

Declare a function named `expandArray()` that:

* Takes no arguments
* Contains a single local variable, `myArray`, which points to [1, 1, 1]
* Returns an anonymous function that directly modifies `myArray` by
  appending another `1` into it
* The returned function then returns the value of `myArray`

*/
function expandArray() {
    const myArray = [1,1,1];
    return function() {
        myArray.push(1);
        return myArray;
    }
}
const array = expandArray();
array();

```



