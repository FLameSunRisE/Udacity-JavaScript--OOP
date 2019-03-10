## Functions are First-Class Functions {#functions-are-first-class-functions}

1. Be stored in variables
2. Be returned from a function.
3. Be passed as arguments into another function.

## Functions Can Return Functions {#functions-can-return-functions}

### Example

* If call alertThenReturn in browser that will show the 'Message 1' However, we don't actually see an alert that says
  `'Message 2!'`, since none of the code from the inner function is executed.

```js
function alertThenReturn() {
  alert('Message 1!');

  return function () {
    alert('Message 2!');
  };
}
```

* How to returned function\('Message 2!'\)

```js
const innerFunction = alertThenReturn();
// alerts 'Message 1!'
innerFunction();
// alerts 'Message 2!'
```



