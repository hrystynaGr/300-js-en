### Compare approaches for working with asynchronous code: callbacks vs. promises vs. async/await.

#### Callbacks
It is the oldest approach to work with asyncronous code.
**+:** callbacks are supported by most APIs, are easy to understand.
**-:** the code is hard to read, using nested callbacks could lead to "callback hell", doesn't have built in mechanism of error catching.
```
function step1(callback) {
    console.log('Step 1 done!');
    callback();
}

function step2(callback) {
    console.log('Step 2 done!');
    callback();
}

function step3(callback) {
    console.log('Step 3 done!');
    callback();
}

step1(function() {
    step2(function() {
        step3(function(){
            console.log('Allsteps done!');
        });
    });
});
```

#### Promises
Was created to avid callback hell, increase readability and make working with asyncronous code easier. 
**+:** avioding "callback hell", has built-in mechanism of error catching.
**-:** not each API supports it, harder to understand in comparison to call backs.
Promise - is an object wchich is not data yet, but will resolve to data or to error sometime in the future.

```
const data = new Promise((res, rej)=> {
    //some fetching here
    if (fetchingSuccessful) {
        resolve(someData);
    } else {
        reject(someError);
    }
}).then((data) => {
    console.log('Fetched sucessfully!');
}).catch((error) => {
    console.log(`Error occured ${error}`);
})
```

#### async/await
Built up on promises. *async* keyword is used to declare a function which has promise, *await* is used to wait for the promise to resolve.
**+:** modern, so little APIs supports it.
**-:** code looks like normal syncronous code.

```
async function fetchData() {
    const data = await fetch('/url-to-fetch);
    console.log(data); // this line will be executed only after promise was resolved
}
```