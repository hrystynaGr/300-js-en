### Can you add new properties/functions to the prototypes of standard classes (Array, Object, etc.)? Why or why not? In what cases can you do it, and how can you safeguard yourself if you need to extend a prototype?

JS alloves to exted existing classes, as Number, Array, object etc., but it is risky to do so. I would consider doing it only to worite polifills, so some methods that are new, and are not supported but older browsers still can be used. 
**What to consider before extending built in class?**
1. Re-think if you really need to extend a build-in class. Maybe you can create another object and write you additional functions there.
```
const myArrayExtension = {
    function addNum(num) {
        //logic
    },
    function removeNum(num) {
        //logic
    },
}
myArrayExtension.addNum(num);
```

2. Be aware of accident re-initialization of already existing methods. Make sure the property you want to add doesn't exist yet. And only then create it.
```
Number.hasOwnProperty('length'); //false
```

3. Keep in mind, third-party code, pr other developers working on the projects, if not aware of changes you made, may depend on the default behaviour of the methods.