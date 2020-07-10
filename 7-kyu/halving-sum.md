# [Halving Sum](https://www.codewars.com/kata/5a58d46cfd56cb4e8600009d/javascript)

 Given a positive integer `n`, calculate the following sum:

`n + n/2 + n/4 + n/8 + ...`


## Syntax

> halvingSum(`number`) -> `number`

### Parameters

**paramName**: `number`

- positive integer

### Return Value: `number`

All elements of the sum are the results of integer division. 

## Examples

`25  =>  25 + 12 + 6 + 3 + 1 = 47`

First example:

```js
const num1 = 25;
const sum1 = halvingSum(num1);
console.log(sum1); // 47
```

Second example:

```js
const num2 = 127;
const sum2 = halvingSum(num2);
console.log(sum2); // 247
```


## [AaronJGoldsmith](https://www.codewars.com/users/AaronJGoldsmith)

```js
function halvingSum(n) {
    if(n === 1) return n;
    return n + halvingSum(Math.floor(n/2));
}
```

### Strategy

Aaron Goldsmith solved this challenge by iterating the given integer as long as it is not equal to 1 and within every iteration he calculated sum of `number` and result of halving this `number`.

### Implementation

AaronJGoldsmith used `if` statement to check if the given integer is equal to one, in this case he returned the same integer. If no - he returned the sum of the integer with result of the `halvingSum` function that divides this number by 2 and returned the largest integer less than or equal to a given number, by using `Math.floor()` method.

**if statement**: this statement executes a block of code if a specified condition is true.

**Math.floor**: rounds a number down and returns an integer value. 


### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `ternary operator`
- `for` loop
- `parseInt`
- `Math.trunc()`
- `map()`

## [ZED.CWT](https://www.codewars.com/users/ZED.CWT)

```js
halvingSum=H=Q=>Q&&Q+H(Q>>1)

```

### Strategy

ZED.CWT solved this challenge by iterating the given integer as long as it is not equal to zero. Within each iteration if the condition is truthy - he calculated the sum of `number` and result of halving this `number`, if the condition is falsy - he returned 0.

### Implementation

In order to understand this function ZED.CWT provided backwards steps of his solution:

 1. Rename H (halvingSum):

`halvingSum = Q => Q && Q + halvingSum(Q >> 1)`

 2. Use ternary operator to check the conditions:

`halvingSum = Q => Q ? Q + halvingSum(Q >> 1) : 0`

3. Use bitwise shift operators :

`x >> 1 === floor(toInt(x) / 2);`

**`halvingSum = Q => Q ? Q + halvingSum(Math.floor(Q / 2)) : 0`**

**Arrow function** it is quite handy since he has one-liners function

**Ternary operator**: he used ternary operator to checked the conditions. It is quite nice way to do it here, since there are no so many cases to check.

**bitwise shift operator** The sign-propagating right shift ( >> ) operator takes two operands. The first operand is an integer, while the second operand is the number of bits of the first operand to be shifted to the right.

**Math.floor**: rounds a number down and returns an integer value.

### Possible Refactors

This strategy could also be implemented with these methods:
- `switch case`
- `ternary operator`
- `for` loop
- `parseInt`
- `Math.trunc()`
- `map()`
- `reduce()`

---

## Notes

That was quite useful for me to check this incredible clean and smart solutions. First time in my life I saw the usage of sign-propagating right shift ( >> ) operator, i learned what it actually means and does. This example was super helpful to understand: 

```js
(170 >> 3) => Math.floor(170 / (2 ** 3)) => Math.floor(170 / 8) => 21
(-170 >> 3) => Math.floor(-170 / (2 ** 3)) => Math.floor(-170 / 8) => -22
```