### Explain the concepts of mutability/immutability? What types are mutable and vice versa?

Immutability means that each time you are trying to modify something, you get a new modified thing, but you are not modifying the initial one.
Let's imagine you have a glass of water, so if you are drinking the water out of it, and it remains the same glass of water but with a changed amount of water in it, it is a mutable glass. An immutable glass is when each time you drink the water, a new glass with a changed amount of water appears, and the water in the initial glass remains unchanged.

> Immutable data are very important for functional development techniques.

```
let a = [1,2,3];
a.push(4);
console.log(a) // [1,2,3,4]
```
As a result, we have changed an "a" array.
But we can create our own (custom) *push* function, which will be immutable:

```
const push = (arr, elem) => {
    let tempArr = [...arr];
    tempArr.push(elem);
    return tempArr;
}
```

Imagine we have two classes, one will be mutable and the second one immutable.

Let's create a mutable class with the method "drink":

```
class MutableGlass extends from Base {
    constructor(what, howMuch) {
        this.what = what;
        this.howMuch = howMuch;
    }

    drink(val) {
        this.howMuch = this.howMuch - val;
        return this;
    }
}
```
Now let's create two glasses out of this class:
```
const glassOne = new MutableGlass("milk", 300); //Glass with 300ml of milk;
const glassTwo = glassOne.drink(100); //creates glassTwo, which will contain on 100ml of milk less than glassOne;
```
Result:
```
console.log(glassOne.howMuch); // 200
console.log(glassTwo.howMuch); // 200
```
So, how should we create the class if we want it to be immutable and we want to have 300ml in the first and 200ml in the second?

```
class ImmutableGlass extends from Base {
    constructor(what, howMuch) {
        this.what = what;
        this.howMuch = howMuch;
    }

    drink(val) {
        return new ImmutableGlass(this.what, this.howMuch-val);
    }
}
```

Now if we do:
```
const glassOne = new MutableGlass("milk", 300); //Glass with 300ml of milk;
const glassTwo = glassOne.drink(100); //creates glassTwo, which will contain on 100ml of milk less than glassOne;
```

We will receive:
```
console.log(glassOne.howMuch); // 300
console.log(glassTwo.howMuch); // 200
```

> Fun fact
> "const" does not allow reassignment of value but does allow mutations. The following code will not produce an error:

```
const a = [1,2,3];
a.push(4);
```

> Fun fact
> Only objects and arrays are mutable in JS. Primitive data types are not.
