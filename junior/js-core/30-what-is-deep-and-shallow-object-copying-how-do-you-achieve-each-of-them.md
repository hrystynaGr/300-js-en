### What is deep and shallow object copying? How do you achieve each of them?

**Deep copy** - creates totally independent copy of object including all nested objects. Changing one object does't leads to change in another.

**Shallow copy** - duplicates the top-level structure of the original object, but the nested objects or arrays within the copied object still reference the same objects as the original. Changing one object leads to a change in another one.

You can achive deep copy only by using Lodash function, or write your own function (the best approach is recursion).

You can create shallowcopies with plenty of approaches. (map(), spread operator(...), concat(), slice(), Object.assign()).

> Object.assign(target, source) - copies from source to target, if some value from source already exists in trget, it overrides it.