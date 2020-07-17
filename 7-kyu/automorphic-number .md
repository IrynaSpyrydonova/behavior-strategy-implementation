# [Automorphic Number ](https://www.codewars.com/kata/5a58d889880385c2f40000aa)

A number is called `Automorphic` number if and only if its square ends in the same digits as the number itself.

_Task_: given a number determine if it Automorphic or not.

## Syntax

> autoMorphic(`number`) -> `string`

### Parameters

**paramName**: `number`

- positive integer

### Return Value: `string`

if true returns "Automorphic" , if no - returns "Not!!"

## Examples

`autoMorphic (13) -->> return "Not!!"`

First example:

```js
const num1 = 76;
const autoMorphicValue1 = autoMorphic(num1);
console.log(autoMorphicValue1); // Automorphic
```

Second example:

```js
const num2 = 225;
const autoMorphicValue2 = autoMorphic(num2);
console.log(autoMorphicValue2); // Not!!
```

Third example:

```js
const num3 = 625;
const autoMorphicValue3 = autoMorphic(num3);
console.log(autoMorphicValue3); // Automorphic
```


## [Maria Quijada](https://www.codewars.com/users/Maria%20Quijada)

```js
const automorphic = n => RegExp(`${n}$`).test(n**2) ? "Automorphic" : "Not!!";
```

### Strategy

Maria Quijada solved this challenge by checking if the square of the given number ends in the same digits as the number itself and return the answer according if its true or false.

### Implementation

Maria Quijada used `regular expressions` to check if the square of the given integer end with the number itself or not. To perform the answer message, she used the ternary operator.

**Ternary operator**: it check if the condition is true - he executed the first part of the expression, if no - the second part is executed.

**Reqex**: Regular expressions are patterns used to match character combinations in strings. 

**test()** method executes a search for a match between a regular expression and a specified string. Returns true or false.


### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `for` loop
- `toString()`
- `slice`
- `Math.pow()`

## [kruxitka](https://www.codewars.com/users/kruxitka)

```js
function automorphic(n){
  return Math.pow(n,2).toString().endsWith(n) ? "Automorphic":"Not!!"
}

```

### Strategy

kruxitka solved this challenge by returning the given number to power of 2, afterwords converting it into the string and checking if this string actually ends with the given number.

### Implementation

In order to complete this challenge, kruxitka implemented **Math.pow()** method, that returns the given number to power of 2, by applying **toString()** method, she converted the output to string and with help of **endsWith()** method, she checked if this string ends with the given number. To check the conditions and return the right message, she used ternary operator.

**Ternary operator**: he used ternary operator to checked the conditions. It is quite nice way to do it here, since there are no so many cases to check.

**toString()**: method converts a number to a string.

**Math.pow**: returns the base to the exponent power, that is, baseᵉˣᵖᴼⁿᵉⁿᵗ.

**endsWith()**: method determines whether a string ends with the characters of a specified string, returning true or false as appropriate.

### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `for` loop
- `regex`
- `test()`
- `slice`

---

## Notes

It was helpful to get to know such a JS method, as **endsWith()**. Usually I used only regex for such a cases, but with this method the code looks clearly.
