### Compare the keywords var, let, and const.

**var** - function scoped, hoisted. If declared not in a function, becomes global variable (accessible from everytwhere in the app) and is assign to a global object, which makes it accessible from the `window` global object.
```
var time = "20:30";
console.log(window.time) // 20:30
```
If called before value was assigned will receive `undefined`.

**let** - block scoped, hoisted. Block scoped means that it is accesible only withing a block and child blocks of where it was declared.
```
if(true) {
    let mom = 'mom'
    console.log('child') // Uncaught ReferenceError: child is not defined
    if(true) {
        let child = 'child'
        console.log(mom); // 'mom'
    }
}
```
If called before value was assigned will receive `ReferenceError`. This behaviour unlike `var`, could help to catch error in earlies phases, than if `undefined` was returned.

**const** - same as `let` but can't be reassigned. (But can be modified)

```
const a = [4,5];
a.push(6);
console.log(a); // [4,5,6];
```
