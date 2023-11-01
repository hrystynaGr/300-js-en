### What is the difference between a function declaration and a function expression?

```
function funcDeclaration() {
    return 'A function declaration';
}

let funcExpression = function () {
    return 'A function expression';
}
```

**Difference between function expressions and function declarations:**

**Hoisting:** Function declarations are hoisted, allowing them to be called before they are defined. In contrast, function expressions cannot be used before their definition.

**Immediate Use:** Function expressions can be utilized right after they are defined. On the other hand, with function declarations, you must wait until the entire script has been parsed.

**As Arguments:** Function expressions can serve as arguments to other functions, whereas function declarations lack this capability.

**Anonymity:** Function expressions can be anonymous, while function declarations must have a name.

**Use a function declaration when:**
1. you need a more readable and understandable function (such as a long function, or one you’ll need to use in different places)
1. an anonymous function won’t suit your needs
1. you need to create a function that is recursive
1. you need to call the function before it is defined

**Use a function expression when:**1. 
1. you need a more flexible function
1. you need a function that isn’t hoisted
1. the function should only used when it is defined
1. the function is anonymous, or doesn’t need a name for later use
1. you want to control when the function is executed, using techniques like immediately-invoked function expressions (IIFE)
1. you want to pass the function as an argument to another function