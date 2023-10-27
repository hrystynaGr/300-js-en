### Describe the purposes and principles of working with collections like Map and Set.

**Map** - is an object, a mutable data type, but you can put anything as a key to this object.

```
new Map() // create a map;
map.set(key, value) // add key value pair;
map.get(key) // get value by the key;
map.has(key) // true/false;
map.delete(key) // deleted key/value pair;
map.clear() // deletea all values from the map;
map.size() // number of pairs in the map;
```
We can iterate through a map, using:

```
map.keys(); // returns keys
map.values(); // returns values
map.entries(); // returns pairs
```
We can set values in a chain because each `set` method returns the map itself.

Let's create a map, set values to it, and iterate through them:

```
let recipeMap = new Map();
recipeMap.set('lemons', 100).set(['water', 'milk'], '150ml');

for(let entry of recipeMap.entries()) {
    console.log(entry); 
}

// 
//['lemons', 100];
//[['water', 'milk'], '150ml']

```


**Set** - is an object, a mutable data type, same as an array, but with no duplicated entries.

```
new Set([iterable]) // creates a set from [iterable] if it is provided, of empty set if it is not provided;
set.add(value) // adds value to the set;
set.has(value) // true/false;
set.delete(value) // deletes value;
set.clear() // deletes all values from the set;
set.size() // number of entries in the set;
```
We can iterate over Set the same as over Map, using `for...of` or `forEach`:

```
let mySet = new Set([1,2,2,2,4,5]);

for (const value of mySet) {
    console.log(value);
}
```

> **Where do we use Map?**
> We can use it for "caching" heavy functions' results. So when a function is called with the same values, we can simply extract the result from the Map, with no need to run it again.

> **Where do we use Set?**
> Maintain a list of event listeners.
> Maintain a list of user permissions.