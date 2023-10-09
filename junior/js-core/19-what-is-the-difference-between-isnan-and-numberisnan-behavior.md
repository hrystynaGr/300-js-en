### What is the difference between isNaN() and Number.isNaN() behavior?

`Number.isNaN()` (ES6) Basically is just
```
is value a number?
yes -> use isNaN() and return the value
no -> return false
```

`Number.isNaN()` is the same as `isNaN()` but without type coersion. 