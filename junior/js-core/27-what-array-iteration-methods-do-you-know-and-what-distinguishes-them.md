### What array iteration methods do you know, and what distinguishes them?

1. `map()` - *immutable* applies a function to each element and returns new array which consists of elements of the oldone with applied function.
```
const newArr = [1,2,3,4].map((el) => el + 5);
console.log(newArr) // [6,7,8,9];
```
2. `forEach()` - applies function to each elemnet in the array. Ignores `Symbols` if applied to objects.
```
let arr = [1, 2, 3];
arr.forEach(()=> console.log(`Hello ${el+1}`));
// Hello 2
// Hello 3
// Hello 4
```
3. `filter()`  - *immutable* creates a new array of elemnts which meet the condition.
```
const newArr = [-1,2,3,4].filter((el) => el > 0);
console.log(newArr) // [-1];
```
4. `find()` - returns first elemnt of the array which meets the condition.
```
const newArr = [-1, 2, 3, -7, 4].find((el) => el > 0);
console.log(newArr) // -1;
```
5. `findIndex()` - returns an index of the first element satisfied the condition. `findLastIndex()` - returns index of a last element satisfing the condition.
```
[1,2,3,4,5].findIndex((el) => el > 4) // 4
```
6. `reduce()` - applies a function to each element and remembers previous state.
```
const numbs = [1,2,3,4].reduce((acc,el) => acc + el);
console.log(numbs) // 10;
```
7. `some()` -  returns `true` if at least one element of the array satisfy the condition, and false othervise.
```
[-2, 3, 4, 5].every((el) => el > 0) // true
```
8. `every()` -  returns `true` if each element of the array satisfy the condition, and false othervise.
```
[-2, 3, 4, 5].every((el) => el > 0) // false
```
