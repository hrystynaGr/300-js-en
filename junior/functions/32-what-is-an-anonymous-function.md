### What is an anonymous function?

Anonimous function is fucntion without name. Only *function expression* can be anonimous (but could be also named).
1. Example on anonimous function expression:
```
const calcSum = function(a, b) {
    retunr a + b;
}
```

1. Example on anonimous function as a callback:
```
setTimeout(function(){
    console.log('One second passed!');
},1000)
```

1. As IIFE (Immediately Invoked Function Expression):
```
(function () {
  console.log('Hello!');
})();
```