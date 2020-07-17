# [Alternate capitalization](https://www.codewars.com/kata/59cfc000aeb2844d16000075)

Given a string, capitalize the letters that occupy even indexes and odd indexes separately, and return as shown below. Index 0 will be considered even.

## Syntax

> capitalize(`string`) -> `array`

### Parameters

**paramName**: `string`

- a lowercase string with no spaces.

### Return Value: `array`

array of strings with capitalized even and odd indexes separately.

## Examples

`capitalize("abcdef") = ['AbCdEf', 'aBcDeF']`

First example:

```js
const str1 = "abcdef";
const capitalizeValue1 = capitalize(str1);
console.log(capitalizeValue1); // ['AbCdEf', 'aBcDeF']
```

Second example:

```js
const str2 = "abracadabra";
const capitalizeValue2 = capitalize(str2);
console.log(capitalizeValue2); // ['AbRaCaDaBrA', 'aBrAcAdAbRa']
```

Third example:

```js
const str3 = "codewarriors";
const capitalizeValue3 = capitalize(str3);
console.log(capitalizeValue3); // ['CoDeWaRrIoRs', 'cOdEwArRiOrS']
```


## [Voile](https://www.codewars.com/users/Voile)

```js
function capitalize(s){
  return [0,1].map(r=>[...s].map((c,i)=>i%2===r?c.toUpperCase():c).join(''));
};
```

### Strategy

Voile solved this challenge by giving a set of numbers, that represent even and odd index of characters in the string and checking them either they are odd or even. If the index of the character is even, she returns it to uppercase, if no - she returns the character by itself. 

### Implementation

Voile assign the array with o and 1 to represent even and odd numbers. Viola used  **map()** twice to call functions for all elements. First *map* provides elements 0 or 1 for the second *map*, that check all elements either they are even or odd.It worked since she convert the string to the array, by using spread operator [...]. She used the ternary operator to check the condition, if index of the character is even, she convert the character to uppercase, if no - she returned the character by itself. In the end she applied **join()** method to convert the elements of the array again into the string.

**Ternary operator**: it check if the condition is true - he executed the first part of the expression, if no - the second part is executed.

**join()**: method returns the array as a string 

**map()**  method creates a new array with the results of calling a function for every array element.

**spread operator** It expands the array into individual elements. So, it can be used to expand the array in a places where zero or more elements are

**toUpperCase()** converts the string to uppercase letters


### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `for` loop
- `split`
- `if else statement`
- `reduce`

## [AlexSnowden](https://www.codewars.com/users/AlexSnowden)

```js
function capitalize(s){
  const odd = s.split("").map((l, i) => i % 2 !== 0 ? l.toUpperCase() : l).join("");
  const even = s.split("").map((l, i) => i % 2 === 0 ? l.toUpperCase() : l).join("");
  return [even, odd];
};
```

### Strategy

AlexSnowden solved this challenge by split the given string by characters and check if the index of every character is even or odd. for the odd numbers if the index is even - he return the character by itself if no - he returned the character to uppercase. For the even numbers he applied the opposite logic (even index - to uppercase, odd index- returned the character by itself).

### Implementation

In order to complete this challenge, AlexSnowden implemented **split()** method, that splits a string into an array of substrings, that allows him to use **map()** method,that calls function to check conditions for each element of the array (to check either the index of elements is even or odd). To check the conditions he used the **ternary operator**, that in case the condition is true - returned even(odd) element to uppercase or , if the condition is false  - returned the element by itself. In the end he applied **join()** method to convert the elements of the array again into the string.

**Ternary operator**: it check if the condition is true - he executed the first part of the expression, if no - the second part is executed.

**join()**: method returns the array as a string 

**map()**  method creates a new array with the results of calling a function for every array element.

**split()** method is used to split a string into an array of substrings, and returns the new array

**toUpperCase()** converts the string to uppercase letters

### Possible Refactors

This strategy could also be implemented with these methods:

- `switch case`
- `for` loop
- `rest parameters`
- `if else statement`
- `reduce`

---

## Notes

### SPREAD Operator with Fun
JavaScript ES6 (ECMAScript 6) introduced the spread operator. The syntax is three dots(...) followed by the array (or iterable*). It expands the array into individual elements. So, it can be used to expand the array in a places where zero or more elements are expected.

1. **Copying an array**

`let fruits = ['Apple','Orange','Banana'];`

`let newFruitArray = [...fruits];`

`console.log(copiedList); // ['Apple','Orange','Banana']`

2. **Concatenating arrays**

`let arr1 = ['A', 'B', 'C'];`

`let arr2 = ['X', 'Y', 'Z'];`

`let result = [...arr1, ...arr2];`

`console.log(result); // ['A', 'B', 'C', 'X', 'Y', 'Z']`

3. **Spreading elements together with an individual element**

`let fruits = ['Apple','Orange','Banana'];`

`let newFruits = ['Cherry', ...names];`

`console.log(newFruits); // ['Cherry', 'Apple','Orange','Banana']`

4. **Spreading elements on function calls**

`let fruits = ['Apple','Orange','Banana'];`

`var getFruits = (f1, f2, f3) => {
console.log(Fruits: ${f1}, ${f2} and ${f3}); };`

`getFruits(...fruits); // Fruits: Apple, Orange and Banana`

5. **Spread syntax for object literals**

`var obj1 = { id: 101, name: 'Jhon Doe' }`

`var obj2 = { age: 25, country: 'USA'}`

`const employee = { ...obj1, ...obj2 }`

`console.log(employee); //{ "id": 101, "name": "Jhon Doe", "age": 25, "country": "USA" }`
