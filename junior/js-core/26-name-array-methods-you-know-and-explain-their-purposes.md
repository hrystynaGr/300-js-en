### Name array methods you know and explain their purposes.
1. `push()` - *mutable* adds an element to the end of the array.
```
const arr = [1,2,3,4];
arr.push(5);
console.log(arr); // [1,2,3,4,5]
```

2. `pop()` - *mutable* deletes last element from the array and returns it.
```
const arr = [1,2,3,4];
const last = arr.pop();
console.log(arr, last) // [1,2,3] 4
```

3. `unshift()` - *mutable* adds an element to the start of the array.
```
const arr = [1,2,3];
arr.unshift(0);
console.log(arr) // [0,1,2,3];
```
4. `shift()` - *mutable* deletes and returns first element of the array

```
const arr = [1,2,3];
const first = arr.shift();
console.log(arr, fist) // [2,3] 1;
```

5. `includes()` - *immutable* returns `true` if item is present in array and `false` if it is not.
```
[1,2,3,4].includes(3); // true
```

6. `every()` -  *immutable* returns `true` if each element of the array satisfy the condition, and false othervise.
```
[-2, 3, 4, 5].every((el) => el > 0) // false
```

7. `some()` -  *immutable* returns `true` if at least one element of the array satisfy the condition, and false othervise.
```
[-2, 3, 4, 5].every((el) => el > 0) // true
```

8. `map()`-  *immutable* applies a function to each element and returns new array which consists of elements of the oldone with applied function.
```
const newArr = [1,2,3,4].map((el) => el + 5);
console.log(newArr) // [6,7,8,9];
```

9. `filter()` - *immutable* creates a new array of elemnts which meet the condition.
```
const newArr = [-1,2,3,4].filter((el) => el > 0);
console.log(newArr) // [-1];
```

10. `find()` - *immutable* returns first elemnt of the array which meets the condition.
```
const newArr = [-1, 2, 3, -7, 4].find((el) => el > 0);
console.log(newArr) // -1;
```

???????????????????????????? is mutable?
11. `sort()` - *mutable* change the order of the elements as spesified in the fucntion.
```
let arr = [1, 2, 3];
arr.sort((a, b) => b-a);
console.log(arr); // [3,2,1];
```

12.  `forEach()` - *immutable* applies function to each elemnet in the array. Ignores `Symbols` if applied to objects.
```
let arr = [1, 2, 3];
arr.forEach(()=> console.log(`Hello ${el+1}`));
// Hello 2
// Hello 3
// Hello 4
```

13. `reduce()` - *immutable* applies a function to each element and remembers previous state.
```
const numbs = [1,2,3,4].reduce((acc,el) => acc + el);
console.log(numbs) // 10;
```

14. `flat(depth)` - *immutable* creates flat array from nested array, to the specified depth. Number of depth should be num of arrays you see -1;
```
[1,2,[3,4,[5,6]]].flat(2) // [1,2,3,4,5,6]
```

15. `indexOf(el)` - *immutable* returns an index of the element in the array.
```
let arr = [1,2,3,4,5];
arr.indexOf(1); // 0
```

16. `join(sep)` - *immutable* creates a string from array, using a separator.
```
let arr = [1,2,3,4];
arr.join('+'); // "1+2+3+4"
```

17. `length` - *immutable* returns length of the array.
```
[1,2,3,4].length // 4
```

18. `reverce()` - *mutable* reverce an order of an array.
```
[1,2,3,4].reverce() // [4,3,2,1]
```

19. `concat()` - *immutable* glues two arrays together.
```
const arr = [1,2];
const arr2 = [3,4];
arr.concat(arr2); // [1,2,3,4];
```

20. `findIndex()` - returns an index of the first element satisfied the condition. `findLastIndex()` - returns index of a last element satisfing the condition.
```
[1,2,3,4,5].findIndex((el) => el > 4) // 4
```

21. slice, splice, with, entries, fill, copyWithin