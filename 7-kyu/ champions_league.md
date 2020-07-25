# [Find how many times did a team from a given country win the Champions League?](https://www.codewars.com/kata/581b30af1ef8ee6aea0015b9)

 This function helps you to calculate how many times the team from a given country win the Champions League.
 
Create a function that takes two arguments:

1) An array of objects which feature the season, the team and the country of the Champions League winner.

2) Country (as a string, for example, 'Portugal')

You function should then return the number which represents the number of times a team from a given country has won. Return 0 if there have been no wins.

## Syntax

> countWins(`object`, `string`) -> `string`

### Parameters

**paramName**: `object`

- the object of seasons, teams and countries;

**paramName**: `string`

- name of the country;


### Return Value: `number`

the number how many times the country won the Champions League.

## Examples

First example:

```js
const winnerList1 = [
  { season: '1996–97', team: 'Borussia Dortmund', country: 'Germany' },
  { season: '1997–98', team: 'Real Madrid', country: 'Spain' },
  { season: '1998–99', team: 'Manchester United', country: 'England' },
  { season: '1999–00', team: 'Real Madrid', country: 'Spain' },
  { season: '2000–01', team: 'Bayern Munich', country: 'Germany' },
  { season: '2001–02', team: 'Real Madrid', country: 'Spain' },
  { season: '2002–03', team: 'Milan', country: 'Italy' },
  { season: '2003–04', team: 'Porto', country: 'Portugal' },
  { season: '2004–05', team: 'Liverpool', country: 'England' },
  { season: '2005–06', team: 'Barcelona', country: 'Spain' },
  { season: '2006–07', team: 'Milan', country: 'Italy' },
  { season: '2007–08', team: 'Manchester United', country: 'England' },
  { season: '2008–09', team: 'Barcelona', country: 'Spain' },
  { season: '2009–10', team: 'Internazionale', country: 'Italy' },
  { season: '2010–11', team: 'Barcelona', country: 'Spain' },
  { season: '2011–12', team: 'Chelsea', country: 'England' },
  { season: '2012–13', team: 'Bayern', country: 'Germany' },
  { season: '2013–14', team: 'Real Madrid', country: 'Spain' },
  { season: '2014–15', team: 'Barcelona', country: 'Spain' },
  { season: '2015–16', team: 'Real Madrid', country: 'Spain' }
];
const country = 'Portugal';
const result = countWins(winnerList1, country);
console.log(result); // 1
```

Second example:

```js
const country1 = 'FootLand';
const result = countWins(winnerList1, country1);
console.log(result); // 0
```

Third example:

```js
const country1 = 'Spain';
const result = countWins(winnerList1, country1);
console.log(result); // 9
```

## [St3f4n](https://www.codewars.com/users/St3f4n)

```js
const countWins = (w, c) => w.filter(a=>a.country === c).length;
```

### Strategy

donaldsebleung solved this challenge by calculating the total amount of happiness rating of the team. To provide the correct answer he checked if the average score of rating bigger than 5 - you can stay in the office, if the average score of rating less than 4 - you have to get out from there.


### Implementation

donaldsebleung implemented his strategy by applying the `Object.keys` function, that returned an array of strings that represent all the enumerable properties of the given object. Afterwards he used `reduce` method to calculate the total amount of the rating. Within `reduce` method, by using ternary operator, he checked also the condition, if the element of the array is equal to boss name, and if yes, the score were for that element were doubled. To find the average amount of the score, he divided the total sum by the quantity of the team members. Using ternary operator donaldsebleung  checked, if the average amount is bigger that 5 or not. If yes - he returns to user `Nice Work Champ!`, if the average amount of rating is less than 5 - he returns to user `Get Out Now!`.

**Object.keys**: The Object.keys() method returns an array of a given object's own enumerable property names, iterated in the same order that a normal loop would.

**reduce()**: The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in single output value.

**Ternary operator**: he used ternary operator to checked the conditions. It is quite nice way to do it here, since there are no so many cases to check.

### Possible Refactors

This strategy could also be implemented with these methods:
- `while` loop
- `switch case`
- `map()`
- `for in` loop
- `for` loop
- `Object.values`

## [v1z](https://www.codewars.com/users/v1z)

```js
function countWins(winnerList, country) {
  return winnerList.reduce((a,b) => a + (b['country'] == country ? 1 : 0), 0);
}
```

### Strategy

magicandcode basically implemented the same logic, it calculated the overall happiness score of the office team and found the average. After that, he checked if the average amount is less than 5 (than the user should leave the office immediately) or more than 5 (than he can stay). 

### Implementation

magicandcode implemented his strategy by applying the `Object.values` function, that  returns an array of a given object's own enumerable property values, after that he applied `reduce` method to find the total score of the happiness of the team members and score of the boss. Afterwards he found the average score of the team, by divided the total amount by the quantity of the team members. His result is depending of the condition, that he checked by teranry operator (either the average score is bigger or less than 5).

**Object.values**: The Object.values() method returns an array of a given object's own enumerable property values, in the same order as that provided by a for...in loop.

**reduce()**: The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in single output value.

**Ternary operator**: he used ternary operator to checked the conditions. It is quite nice way to do it here, since there are no so many cases to check.

### Possible Refactors

This strategy could also be implemented with these methods:
- `while` loop
- `switch case`
- `map()`
- `for in` loop
- `for` loop
- `Object.keys`

---

## Notes

This exercises provide nice example how we can use Object.keys and Objects. values functions, when we are dealing with the objects.
