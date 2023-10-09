### How can you check if a variable is equal to NaN?

1. `isNaN()`
2. `Number.isNaN()` (ES6) Basically it is just
```
is value a number?
yes -> use isNaN() and return the value
no -> return false
```
3. `value !== value ()` - *NaN* is the only data structure that is not equal to itself.
