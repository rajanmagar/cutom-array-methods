# Cutom Array Methods
Creating custom map, filter, and reduce JavaScript methods.

To the folks who don't know about higher order functions, here's what Wikipedia says: Higher order functions can be best described by the map, filter and reduce functions.  Today, we will be writing our own map, filter and reduce functions.

## Array.prototype.map()

According to [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

> The `map()` method creates a new array with the results of calling a provided function on every element in the calling array.
Seems really simple. Let's check out the Javascript map() in action right now!

```javascript
let arr = [1, 2, 3, 4, 5];

// pass a function to map
const squareArr = arr.map(num => num ** 2);

console.log(squareArr); 
// prints [1, 4, 9, 16, 25]

```

Let's look at detailed instructions for writing our own map function.
- Make a new empty array called mapArr.
- Loop through the items in an array.
- With the current element as the parameter, use the mapFunc method.
- Push the mapFunc function's output onto the mapArr array.
- After going over every element, return the mapArr array.

```javascript
// map takes an array and function as argument
function customMap(arr, mapFunc) {    
  const mapArr = []; // empty array        
  // loop though array    
  for(let i=0; i < arr.length; i++) {        
    const result = mapFunc(arr[i], i, arr);        
    mapArr.push(result);    
  }    
  return mapArr;
}

const squareArr2 = customMap(arr, num => num ** 2);

console.log(squareArr2); // prints [1, 4, 9, 16, 25]
```

Isn't it cool? Now let's look at filter().

## Array.prototype.filter()

According to [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

> The `filter()` method creates a shallow copy of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function.

Let’s see an example:

```javascript
let arr = [1, 2, 3, 4, 5];

// pass a function to map
const evenNumbers = arr.filter(num => num % 2 === 0);

console.log(evenNumbers); 
// prints [2, 4]

```

Let’s go through step by step on how the filter() works.
- Make an empty array called filterArr.
- Continually iterate over the array's components.
- called the filterFunc function with the current element as the parameter.
- Push the element to the filterArr array if the result is true.
- After passing over every element, return the filterArr array.

```javascript
// filter takes an array and function as argument
function customFilter(arr, filterFunc) {    
  const filterArr = []; // empty array        
  // loop though array    
  for(let i=0;i<arr.length;i++) {        
    const result = filterFunc(arr[i], i, arr);        
    // push the current element if result is true        
    if(result)             
      filterArr.push(arr[i]);     
  }    
  return filterArr;
}

const evenNumbers2 = customFilter(arr, num => num % 2 === 0);

console.log(evenNumbers2); 
// prints [2, 4]
```
