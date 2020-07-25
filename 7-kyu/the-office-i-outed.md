# [The Office I - Outed](https://www.codewars.com/kata/57ecf6efc7fe13eb070000e1/javascript)

 This function helps you to calculate the happiness rating of your colleagues at your office.
 
Your colleagues have been looking over you shoulder. When you should have been doing your boring real job, you've been using the work computers to smash in endless hours of codewars.

In a team meeting, a terrible, awful person declares to the group that you aren't working. You're in trouble. You quickly have to gauge the feeling in the room to decide whether or not you should gather your things and leave.

Given an object (meet) containing team member names as keys, and their happiness rating out of 10 as the value, you need to assess the overall happiness rating of the group. If <= 5, return 'Get Out Now!'. Else return 'Nice Work Champ!'.

Happiness rating will be total score / number of people in the room.

Note that your boss is in the room (boss), their score is worth double it's face value (but they are still just one person!).

## Syntax

> outed (`object`, `string`) -> `string`

### Parameters

**paramName**: `object`

- the object of team member names as keys, and their happiness rating out of 10 as the value;

**paramName**: `string`

- name of your boss;


### Return Value: `string`

the overall happiness rating of the group

## Examples

First example:

```js
const meet = {'tim':0, 'jim':2, 'randy':0, 'sandy':7, 'andy':0, 'katie':5, 'laura':1, 'saajid':2, 'alex':3, 'john':2, 'mr':0};
const boss = 'laura';
const result = outed(meet, boss);
console.log(result); // 'Get Out Now!'
```

Second example:

```js
const meet = {'tim':2, 'jim':4, 'randy':0, 'sandy':5, 'andy':8, 'katie':6, 'laura':2, 'saajid':2, 'alex':3, 'john':2, 'mr':8};
const boss = 'john';
const result = outed(meet, boss);
console.log(result); // 'Get Out Now!'
```

Third example:

```js
const meet = {'tim':1, 'jim':3, 'randy':9, 'sandy':6, 'andy':7, 'katie':6, 'laura':9, 'saajid':9, 'alex':9, 'john':9, 'mr':8};
const boss = 'katie';
const result = outed(meet, boss);
console.log(result); // 'Nice Work Champ!'
```

## [donaldsebleung](https://www.codewars.com/users/donaldsebleung)

```js
function outed(c, b) {
  return Object.keys(c).reduce((s, e) => s + c[e] * (e === b ? 2 : 1), 0) / Object.keys(c).length > 5 ? "Nice Work Champ!" : "Get Out Now!";
}
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

## [magicandcode](https://www.codewars.com/users/magicandcode)

```js
function outed(meet, boss){
  const ratings = Object.values(meet);
  const totalScore = ratings.reduce((sum, rating) => sum += rating) + meet[boss];
  return totalScore / ratings.length > 5 ? 'Nice Work Champ!' : 'Get Out Now!';
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
