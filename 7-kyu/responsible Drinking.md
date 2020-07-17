# [Responsible Drinking](https://www.codewars.com/kata/5aee86c5783bb432cd000018)

Codewars Bar recommends you drink 1 glass of water per standard drink so you're not hungover tomorrow morning.

Your fellow coders have bought you several drinks tonight in the form of a string. Return a string suggesting how many glasses of water you should drink to not be hungover.

## Syntax

> hydrate(`string`) -> `string`

### Parameters

**paramName**: `string`

- a string with the list of the drinks that you had

### Return Value: `array`

- a string with the answer how many water you have to drink in order do not have hungover tomorrow morning.

## Examples

`"1 beer"  =>  "1 glass of water"`
`"1 shot, 5 beers and 1 glass of wine"  =>  "7 glasses of water"`

First example:

```js
const str1 = '1 beer';
const hydrateValue1 = hydrate(str1);
console.log(hydrateValue1); // "1 glass of water"
```

Second example:

```js
const str2 = "2 glasses of wine and 1 shot";
const hydrateValue2 = hydrate(str2);
console.log(hydrateValue2); // "3 glasses of water"
```

Third example:

```js
const str3 = "1 shot, 5 beers, 2 shots, 1 glass of wine, 1 beer";
const hydrateValue3 = hydrate(str3);
console.log(hydrateValue3); // "10 glasses of water"
```


## [stɛffan153](https://www.codewars.com/users/st%C9%9Bffan153)

```js
const hydrate = (s, w = [...s].filter(x => !isNaN(x)).reduce((a, b) => a + +b, 0)) => `${w} glass${w === 1 ? '' : 'es'} of water`;
```

### Strategy

stɛffan153 solved this challenge by checking the given string and tried to identify the given numbers among the words and calculating the total amount of them. The final message depends on either the total amount of numbers is bigger than one or not.

### Implementation

stɛffan153 convert the given string into the array by using spread operator, afterwards he filter through array with **filter()** method checking either element is number or string with **isNaN** method. If the element of the array is number he calculated it every time to the total amount, by applying **reduce()** method. Afterwords he return the final message, that depends either the total amount is bigger than 1 or not. The conditions stɛffan153 checked by use of ternary operator.

**Ternary operator**: it check if the condition is true - he executed the first part of the expression, if no - the second part is executed.

**filter ()**: method creates a new array with all elements that pass the test implemented by the provided function.

**isNaN()** function determines whether a value is an illegal number (Not-a-Number)

**spread operator** It expands the array into individual elements. So, it can be used to expand the array in a places where zero or more elements are

**reduce()** method reduces the array to a single value.


### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `for` loop
- `map`
- `match`
- `reduce`
- `split`

## [defo550](https://www.codewars.com/users/defo550)

```js
function hydrate(s) {
  const reducer = (accumulator, currentValue) => accumulator + currentValue;
  const formatGlass = n => n > 1 ? 'glasses' : 'glass';
  const numberOfDrinks = s
    .match(/\d/g)
    .map(Number)
    .reduce(reducer);
    
  return `${numberOfDrinks} ${formatGlass(numberOfDrinks)} of water`;
}
```

### Strategy

defo550 solved this challenge by checking in the given string digit characters and if he found them, he converted them to number and calculated the total sum of them. Depending on the final sum (either it is more than 1) he provided the final message.

### Implementation

In order to complete this challenge, defo550 implemented **match()** method with **regular expression** `/\d/g` to find either the given string contain digits characters globally, then converting them to number by using **Number** method and calculated the total sum with **reduce** method. To provide the appropriate answer, he applied **ternary operator** for checking the given conditions (either total sum is bigger that 1 or not).

**Ternary operator**: it check if the condition is true - he executed the first part of the expression, if no - the second part is executed.

**reduce()**: method reduces the array to a single value (). in this case it returns the total sum of all numbers).

**map()**  method creates a new array with the results of calling a function for every array element.

**match()**  method searches a string for a match against a regular expression, and returns the matches, as an Array object.

**Reqex**: Regular expressions are patterns used to match character combinations in strings (in this particular example it means "Do a global search for digits");

### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `for` loop
- `filter`
- `isNaN()`
- `split`

---

## Notes

I was confused a bit about **map(Number)**.
[Here](https://stackoverflow.com/questions/48343478/what-does-mapnumber-do-here) I found quite good explanation:
*map(Number)* is equivalent to `map((str, ind, arr) => Number(str, ind, arr))`

The reason Number works despite passing extra arguments in is because it ignores everything but the first argument. You cannot expect every function to behave accordingly, since not all functions ignore everything but the first argument, but in this case it is a convenient shortcut. Another neat example that works well is converting truthy and falsy values to booleans:

`var arrBool = arrAny.map(Boolean);`
