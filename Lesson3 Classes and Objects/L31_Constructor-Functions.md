### Creating a New Object {#creating-a-new-object}

```js
let developer = new SoftwareDeveloper();
```

### Creating Multiple Objects {#creating-multiple-objects}

```js
let engineer = new SoftwareDeveloper();
let programmer = new SoftwareDeveloper();

console.log(engineer);
// SoftwareDeveloper { favoriteLanguage: 'JavaScript' }

console.log(programmer);
// SoftwareDeveloper { favoriteLanguage: 'JavaScript' }
```

### Constructor Functions Can Have Parameters {#constructor-functions-can-have-parameters}

```js
function SoftwareDeveloper(name) {
  this.favoriteLanguage = 'JavaScript';
  this.name = name;
}
```

### Question:![](/assets/L3_1Q1.png)![](/assets/L3_1Q2.png)

### Question:

```js
/*

Now it's your turn to create a constructor function. Declare a
`Sandwich` constructor function that takes three parameters:

1. `bread` (string) - the type of bread for the sandwich (e.g. "Wheat")
2. `meat` (array) - the meats to put on the sandwich
   (e.g. `[]` for a vegetarian sandwich!)
3. `vegetables` (array) - the vegetables to include in the sandwich

*/

function Sandwich(bread,meat,vegetables){
    this.bread = bread;
    this.meat = meat ;
    this.vegetables = vegetables;
}

 let Sand = new Sandwich("wheat",['Chorizo','Prosciutto','Pancetta'],['Garlic','Cucumber','Mushrooms']);
```

## Seeing the Object's Constructor \(`instanceof`\) {#seeing-the-object-s-constructor-instanceof-}

```js
function Developer(name) {
  this.name = name;
}

let dev = new Developer('Veronika');

typeof dev
// "object"

dev instanceof Developer;
// true
```

### Question :

Consider the following constructors:

```js
function Finch(name) {
  this.kingdom = 'Animalia';
  this.name = name;
}

function Sparrow(name) {
  this.kingdom = 'Animalia';
  this.name = name;
}
```

Let's create an instance of each constructor:

```js
const atticus = new Finch('Atticus');
const jack = new Sparrow('Jack');
```

What is the result when`atticus instanceof Sparrow;`is executed?

* Ans: False
* Solution:
  false is returned. Not only is Sparrow not the atticus object's constructor function -- the Sparrow object is nowhere to be found in atticus's prototype chain.



