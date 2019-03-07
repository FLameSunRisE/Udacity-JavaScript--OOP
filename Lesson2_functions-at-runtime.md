## closure  {#functions-retain-their-scope}

* This process of a function retaining access to its scope
  * The function itself

  * The code \(but more importantly, the _scope chain of_\) where the function is declared

MDN defines a closure as:

> "the combination of a function and the lexical environment within which that function was declared."



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



