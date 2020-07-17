# [London CityHacker](https://www.codewars.com/kata/5bce125d3bb2adff0d000245/javascript)

 This function helps you to calculate the total cost of the journey and return the cost rounded to 2 decimal places in the format (where x is a number): £x.xx.
 
 Journeys will always only contain a combination of tube names and bus numbers. Each tube journey costs **£2.40** and each bus journey costs **£1.50**. If there are 2 or more adjacent bus journeys, the bus fare is capped for sets of two adjacent buses and calculated as one bus fare for each set.

## Syntax

> londonCityHacker(`array`) -> `string`

### Parameters

**paramName**: `array`

- the array contains bus numbers and TFL tube names as strings;

### Return Value: `string`

total cost of the journey, rounded to 2 decimal places in the format (where x is a number): £x.xx

## Examples

First combination:

```js
const journey1 = [12, 'Central', 'Circle', 21];
const totalCost1 = londonCityHacker(journey1);
console.log(totalCost1); // "£7.80"
```

Second combination:

```js
const journey2 = ['Piccidilly', 56];
const totalCost2 = londonCityHacker(journey2);
console.log(totalCost2); // "£3.90"
```

Third combination:

```js
const journey3 = [386, 56, 1, 876];
const totalCost3 = londonCityHacker(journey3);
console.log(totalCost3); // "£3.00"
```

## [Chrono79](https://www.codewars.com/users/Chrono79)

```js
function londonCityHacker(journey) {
  let sum = 0;
  
  for (let i = 0; i < journey.length; i++) {
    if (typeof journey[i] === "string") sum += 2.40;
    else {
      sum += 1.50;
      if (typeof journey[i + 1] === "number") i++;
    }  
  }
  
  return `£${sum.toFixed(2)}`;
}
```

### Strategy

Chrono79 solved this challenge by iterating over the items in an array and check if those items are meeting conditions(type of item is equal to "string"). If yes, he increments the total amount of costs by the tube journey costs(2.40), if no - he increments the total amount of costs by bus journey costs (1.50).


### Implementation

Chrono79 implemented his strategy by declare fist sum, that is equal to zero and  writing `for` loop to iterate over the items in an array and increment the initial sum by journey costs. In order to check the conditions, Chrono79 used `if else` statement. In order to get the correct format of the final result, Chrono79 implement `toFixed()` method to rounding the number to keep only two decimals.

**For loop**: he iterate over the all items in an array.

**If else statement**: he check if the item meet the condition and based on the result, he increment the total sum by appropriate amount of costs.

**toFixed()**: by choosing this method, Charono79 rounding the number to keep only two decimals.

### Possible Refactors

This strategy could also be implemented with these methods:
- `while` loop
- `switch case`
- `map()`
- `for of` loop
- `Arrow function`

## [JohanWiltink](https://www.codewars.com/users/JohanWiltink)

```js
function londonCityHacker(journey) {
  let busFare = 0;
  return `£${
    journey.map( v => isNaN(v) ? ( busFare = 0 , 2.4 ) : busFare = 1.5 - busFare )
           .reduce( (v,w) => v+w , 0 )
           .toFixed(2)
  }`;
}
```

### Strategy

JohanWiltink solved this challenge by iterate over an array and calling function on every element of array, which checks these elements for conditions and increment the total amount of costs.


### Implementation

JohanWiltink implemented his strategy by using map method, that iterate over an array and calling isNaN function to check either the element is NaN and depending either result of the function is true or false, he increment the total amount of journey costs by implementing reduce method. In order to get the correct format of the final result, JohanWiltink implement `toFixed()` method to rounding the number to keep only two decimals.

**map()**: he iterated over an array and calling function on every element of array.

**Ternary operator**: he used ternary operator to checked the conditions. It is quite nice way to do it here, since there are no so many cases to check.

**reduce()**: he used reduce method to calculate the total of a numbers array
**toFixed()**: by choosing this method, Charono79 rounding the number to keep only two decimals.

### Possible Refactors

This strategy could also be implemented with these methods:
- `while` loop
- `switch case`
- `for` loop
- `for of` loop
- `Arrow function`

---

## Notes

This exercises demonstrated me how my code can be more nicer and cleaner with such methods, like `map()` and `reduce()`, rather than with `for` loop and `if else` statements. 