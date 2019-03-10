

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



