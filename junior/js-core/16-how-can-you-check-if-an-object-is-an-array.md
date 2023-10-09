### How can you check if an object is an array?

1. Using the `Array.isArray()` method.
2. Using instanceof:
```
Array instanceof myArray; // true is myArray is an array and false othervise.
```
3. Using constructor:
```
myArray.constructor === Array // true is myArray is an array and false othervise.
```
