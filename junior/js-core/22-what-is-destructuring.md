### What is destructuring?

Destructuring is a mechanism introdused in (ES6), which hels to extract data from objects easily.
1. Destructuring from object:
```
const person = {
    name: 'Jack',
    age: 30
}
const {name, age} = person;
console.log(name, age) // 'Jack' 30
```
Similar way we can destructure from nested object:
```
const person = {
    name: {firstName: 'Jack', lastName: 'Bill'},
    age: 30
}
const {name: {firstName, lastName}, age} = person;
console.log(firstName, lastName, age) // 'Jack' 'Bill' 30
```

2. Destructuring an array:
```
const amounts = [200, 300];
const [lemons, apples] = amounts;
console.log(lemons, apples)// 200, 300
```
Skipping elements in an array:
```
const amounts = [200, 300, 600, 50, 250, 830];
const [lemons,,,,apples] = amounts;
console.log(lemons, apples)// 200, 250
```
Destructuring nested array: 
```
const amounts = [200, ['300', '600'], 50, 250, 830];
const [lemons,[apples, plums], grapes] = amounts;
console.log(lemons, apples, plums, grapes); // 200 '300' '600' 50
```

> You can destructure iterative objects, means, you can destructure strings for example.
```
let hello = 'Hello!'
const [a,,,,,b] = hello;
console.log(a, b) // H !
```
