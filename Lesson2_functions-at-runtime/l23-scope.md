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

  


