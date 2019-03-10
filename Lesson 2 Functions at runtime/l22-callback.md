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

### forEach\(\)

```js
const favoritFlavors = ['cookie','salted caramel','toffee'];
favoritFlavors.forEach(function (flavor){
    console.log('I enjoy '+ flavor + ' ice cream')
});

//I enjoy cookie ice cream
//I enjoy salted caramel ice cream
//I enjoy toffee ice cream
```

### **     **map\(\)

* map\(\) returns a new array based on what's returned from the callback function.

```js
const names = ['David', 'Richard', 'Veronika'];

const nameLengths = names.map(function(name) {
  return name.length;
});

// map() on the names array and pass it an anonymous function as an argument:
names.map(function(name) {
  return name.length;
});
```

### Q2:

```js
/* Using map()
 *
 * Using the musicData array and map():
 *   - Return a string for each item in the array in the following format:
 *     <album-name> by <artist> sold <sales> copies
 *   - Store the returned data in a new albumSalesStrings variable
 *
 * Note:
 *   - Do not delete the musicData variable
 *   - Do not alter any of the musicData content
 *   - Do not format the sales number; leave it as a long string of digits
 */

const musicData = [
    { artist: 'Adele', name: '25', sales: 1731000 },
    { artist: 'Drake', name: 'Views', sales: 1608000 },
    { artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
    { artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
    { artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
    { artist: 'Original Broadway Cast Recording', 
      name: 'Hamilton: An American Musical', sales: 820000 },
    { artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
    { artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
    { artist: 'Rihanna', name: 'Anti', sales: 603000 },
    { artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];

const albumSalesStrings = musicData.map(function(data) {
    return data.name + " by " + data.artist + " sold " + data.sales + " copies";
});

console.log(albumSalesStrings);

```



## filter\(\) {#filter-}

Array's`filter()`method is similar to the`map()`method:

* It is called on an array
* It takes a function as an argument
* It returns a new array 

```js
const shortNames = names.filter(function(name) {
  return name.length < 6;
});

console.log(shortNames);
// ['David']
```

### Q3:

```js
/* Using filter()
 *
 * Using the musicData array and filter():
 *   - Return only album objects where the album's name is
 *     10 characters long, 25 characters long, or anywhere in between
 *   - Store the returned data in a new `results` variable
 *
 * Note:
 *   - Do not delete the musicData variable
 *   - Do not alter any of the musicData content
 */

const musicData = [
    { artist: 'Adele', name: '25', sales: 1731000 },
    { artist: 'Drake', name: 'Views', sales: 1608000 },
    { artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
    { artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
    { artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
    { artist: 'Original Broadway Cast Recording', 
      name: 'Hamilton: An American Musical', sales: 820000 },
    { artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
    { artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
    { artist: 'Rihanna', name: 'Anti', sales: 603000 },
    { artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];

const results = musicData.filter(function(data) {
    if (data.name.length >= 10 && data.name.length <= 25) {
        return data.name;
    }
});

console.log(results);
```



