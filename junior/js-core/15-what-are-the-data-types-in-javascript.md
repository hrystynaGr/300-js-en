### What are the data types in JavaScript?

There are primitive and non-primitive data types in JS. Primitive types are:

1. Boolean
2. Number
3. String
4. Symbol (added in ES6)
5. undefined
6. BigInt

Non-primitive:

1. Objects (Arrays, Objects, Map, Set, WeakMap, WeakSet, Date() etc.)
2. null

> You can use `typeof` to determine the data type; however, it will be helpful only for primitive data types. For non-primitive types, it will always return `object`.

```
let a = 'hey';
let arr = [1,2,3];
console.log(typeof a); // String
console.log(typeof arr); // Object
```

> To define an Object type, you can use `instanceof`.

```
[] instanceof Array; // true
{} instanceof Object; // true
```


> One of JS memes is that `typeof null` will result in `object`. This was a mistake in earlier JS versions, and it is kept like that due to compatibility.

1. Boolean

```
Boolean(undefined) //false
Boolean(0) //false
Boolean('') //false
Boolean(false) //false
Boolean(null) //false
Boolean(NaN) //false
```

4. Symbol is always unique, even if it is described as the same literal.

```
let a = Symbol('hello');
let b = Symbol('hello);
console.log(a === b) //false;
```
> It is common to use Symbols for object keys; this way, they will never be unintentionally mutated:

```
let person = {name: 'John', id: 27}
//now enothe program has line
person.id = 00;
//now console.log(person.id) // 00
```
> But if we create it with Symbol, we can prevent this change

```
let id = Symbol('id');
let person = {name: 'John', [id]: 27}
```


We can create Symbols:

```
let symb = Symbol('id')
```
Access Symbols: 
```
console.log(symb) // Symbol('id')
```

Access description of a Symbol:
```
console.log(symb.description) //  // 'id'
```

Symbols are not iterable in *for...in*:
```
let person = {name: 'John', [id]: 27}

for (let key in person) {
    console.log(key); // only name will be logged
}
```


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

**WeakMap** - same as Map, as only objects are allowed as keys, and when there is no other reference to an object from elsewhere than the key in WeakMap, its key-value gets removed from memory and from the WeakMap.

```
let wMap = new WeakMap();
let a = {1:'1', 2:'2'};
wMap.set(a, 'first_val').set({1:'11', 2:'22'}, 'second_val');
a = null;
wMap.has(a); // false

```
We can't iterate over WeakMap. It has only the following methods:

```
new WeakMap() // create a map;
map.set(key, value) // add key value pair;
map.get(key) // get value by the key;
map.has(key) // true/false;
map.delete(key) // deleted key/value pair;
```

> **Where do we use WeakMap?**
> Often, it is used for working with third-party libraries when you do not know how long something exists there, but you need to get rid of it as soon as it disappears in that library code. So you put the object as a key to the WeakMap, and as soon as it disappears there, it will disappear from the WeakMap.

> **Where do we use Map?**
> We can use it for "caching" heavy functions' results. So when a function is called with the same values, we can simply extract the result from the Map, with no need to run it again.

**WeakSet** - same as Set but can store only objects. An object exists in the WeakSet only if it is reachable from somewhere else.
Methods WeakSet supports:


**WeakSet** - same a Set but can store only objects. Object exists in the WeakSet obly of it is reachable from somewhere else.
Methods WeakSet supports:
```
set.add(value) // adds value to the set;
set.has(value) // true/false;
set.delete(value) // deletes value;
```
We can't iterate through the WeakSet.
