### What are the purposes of setTimeout and setInterval methods?

**setTimeout** - will call the calback function after a sertain amount of time passed. 
```
setTimeout(function, time(in miliseconds));
```

**setInterval** - will call the callback function repeatedly in timeIntervals set, untill process is stopped;
```
setInterval(function, time(in miliseconds));
```
```
let message = 0;
const myTimer = setInterval(()=> {
    console.log(message++);
    if(message > 5) {
        clearInterval(myTimer)
    }
}
, 200)
```

**Examples of usage**
1. Displaing countdown.
2. Animations.
3. Carousels.
4. User session timeout (there are better ways).
5. Repeatedly updating something.

**How setTimeout and setInterval work under the hood**
1. You cann setTimeout with callback function and intervall.
2. JS schedule the envokation of the function with the delay you have specified.
3. Callback function is placed in a "times queue" by JS.
4. The event loop is going over and over to check if there is anything ready to be executed.
5. When the time delay of the callback functions runs off, JS re-place from timer queue to callbackqueue
6. Event loop, if not occupied with something else at the moment, picks up the function from the callback and executes it.