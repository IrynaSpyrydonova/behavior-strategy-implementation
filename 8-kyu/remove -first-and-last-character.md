# [Remove First and Last Character](https://www.codewars.com/kata/56bc28ad5bdaeb48760009b0/train/javascript)

  This function removes the first and last characters of a string. 

## Syntax

> removeChar(`string`) -> `string`

### Parameters

**paramName**: `string`

- the origin string, from which should be removed the first and last character

### Return Value: `string`

- the string, that doesn't include first and last character from the original one.

## Examples

First example:

```js
const string1 = 'eloquent';
const stringAfterRemove1 = removeChar(string1);
console.log(stringAfterRemove1); // 'loquen'
```

Second example:

```js
const string2 = 'country';
const stringAfterRemove2 = removeChar(string2);
console.log(stringAfterRemove2); // 'ountr'
```

Third example:

```js
const string3 = 'person';
const stringAfterRemove3 = removeChar(string3);
console.log(stringAfterRemove3); // 'erso'
```

## [ooflorent](https://www.codewars.com/users/ooflorent)

```js
function removeChar(str) {
  return str.slice(1, -1);
}
```

### Strategy

This task is quite simple, so by using JS method Ooflorent was quite straightforward by doing what the task actually asks to do: delete first and last characters.


### Implementation

In order to complete this challenge, Ooflorent implemented **slice()** method, that selects the elements starting at the given start argument, and ends at, but does not include, the given end argument, `start` and `end` represent the index of items in that array (index 1 - starts from second element, index-1 - the last element).

**slice()**: he extracts parts of a string and returns the extracted parts in a new string.

### Possible Refactors

This strategy could also be implemented with these methods:
- `splice()`
- `pop()`
- `shift()`
- `indexOf()`
- `join()`
- `substring()`
- `substr()`

## [Jotha](https://www.codewars.com/users/Jotha)

```js
function removeChar(str){
 return str.substring(1, str.length-1);
};
```

### Strategy

Jotha solved this challenge by choosing very clever and uncomplicated way by returning exact part of the string that we need.

### Implementation

Jotha implemented his strategy by using *substring()* method, that returns part of the string between startIndex & endIndex. It excludes the endIndex character or up to the end of the string (index 1 - starts from second element, str.length-1 - the last element)

**substring()**: this method extracts the characters from a string, between two specified indices, and returns the new sub string.

### Possible Refactors

- `splice()`
- `slice()`
- `pop()`
- `shift()`
- `indexOf()`
- `join()`
- `substr()`

---

## Notes

I have discovered so many methods that can easily replace each other and in the end give you the same result. It is always necessary to understand differences between them, like what parameters they take, either they modify the original string/array or not and etc in order to get the final result, that you need.