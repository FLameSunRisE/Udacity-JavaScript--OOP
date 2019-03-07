## Function Declarations vs. Function Expressions {#function-declarations-vs-function-expressions}

* Function Declarations
  * A function _declaration_defines a function and does not require a variable to be assigned to it. It simply declares a function, and doesn't itself return a value.

  * example

  ```js
  function returnHello() {
    return 'Hello!';
  }
  ```
* function _expression_

  * Function expressions can be anonymous or named, and are part of another expression's syntax.

  * example

  ```js
  // anonymous
  const myFunction = function () {
    return 'Hello!';
  };

  // named
  const myFunction = function returnHello() {
    return 'Hello!';
  };
  ```



## Immediately-Invoked Function Expressions: Structure and Syntax {#immediately-invoked-function-expressions-structure-and-syntax}

* An immediately-invoked function expression, or IIFE \(pronounced iffy\), is a function that is called immediately after it is defined.

```js
(function sayHi(){
    alert('Hi there!');
  }
)();

// alerts 'Hi there!'
```

* passing argument to IIFE's

```js
(function (name){
    alert(`Hi, ${name}`);
  }
)('Andrew');

// alerts 'Hi, Andrew'
```



## IIFE's, Private Scope, and Event Handling {#iife-s-private-scope-and-event-handling}

* HTML file

```HTML
<!-- button.html -->

<html>

  <body>

     <button id='button'>Click me!</button>

     <script src='button.js'></script>

  </body>

</html>
```

* button.js

```js
// button.js

button.addEventListener('click', (function() {
  let count = 0;

  return function() {
    count += 1;

    if (count === 2) {
      alert('This alert appears every other press!');
      count = 0;
    }
  };
})());
```

### Q1:The following immediately-invoked function expression is run in the browser:

```js
(function(n){
  delete n;
  return n;
})(2);
```

What is the return value?

* Ans: 2
* Solution:The key to this quiz is the result of using the delete operator. The delete operator is actually only effective on an object's properties; it isn't used to directly deallocate resources \(i.e., free up memory\), and has no effect on variables or names of functions.



