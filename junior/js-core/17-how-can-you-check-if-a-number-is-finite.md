### How can you check if a number is finite?

1. Using `isFinite(num)` function.
2. Comparing a number to `+Infinity` and `-Infinity`.
3. Comparing if number is smaller than `Number.MAX_VALUE` amd bigger than `-Number.MAX_VALUE`.
4. `Number.isFinite()` (ES6).

> Difference between `isFinite()` and `Number.isFinite()` is that `Number.isFinite()` doesn't perform type coesion. Unlike `isFinite()`, `Number.isFinite()` won't return true for non-numeric values like strings or objects.