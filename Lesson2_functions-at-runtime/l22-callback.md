## Callback Functions {#callback-functions}

* A function that is passed as an argument to another funcion
* A function that takes another function in as an argument is a higher-order function
* Leveraging callbacks is possible JavaScript functions are first-class functions.

### Q1:

Consider the following two functions:

```js
function each(array, callback) {
  for (let i = 0; i < array.length; i++) {
    if (callback(array[i])) {
      console.log(array[i]);
    }
  }
}
```

```js
function isPositive(n) {
  return n > 0;
};
```

The following is then executed:

`each([-2,7,11, -4, -10], isPositive);`

What is outputted to the console?

* Ans: 7, 11



## Array Methods {#array-methods}

## forEach\(\) {#foreach-}

```js
const favoritFlavors = ['cookie','salted caramel','toffee'];
favoritFlavors.forEach(function (flavor){
    console.log('I enjoy '+ flavor + ' ice cream')
});

//I enjoy cookie ice cream
//I enjoy salted caramel ice cream
//I enjoy toffee ice cream
```

**    
**

