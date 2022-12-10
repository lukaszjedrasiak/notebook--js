## basics
1. The `fetch` API is used to send and/or receive data from a service (an API) without reloading the page.
2. Syntax: `fetch("URL")`
3. Fetch always returns [[promises]]

## fetching json
So, because `fetch(URL)` returns a promise, we can resolve the promise with a .then(callback). This callback will run sometime in the future when the fetch request has been completed.

```js
const api = fetch('URL').then(response => response.json()).then(data => console.log(data));
```

Also, this callback will receive as a first argument the response from the request that we sent. You can call this argument whatever you want, however, we recommend that you call it response.

Just like how fetch(URL) returns a promise, the response.json() method also returns a promise. This means that we cannot read its result directly. Instead, we have to resolve the promise with .then(callback).

1. Fetch returns a `"first" promise`
2. `response.json()` returns a `"second" promise`
3. The second callback at last returns a JSON object.

## access to fetched data
Access to fetched data is allowed only within the second callback.

**Just put a function defined earlier inside this callback**

```js
const api = fetch('URL')
	.then(response => response.json())
	.then(data => {
		console.log(data);
		//access to the json fields i.e
		randomFunc(data.choosenField);
	});
```

BUT - for now it seems to be enough for me.

Fetching method found on web: https://codepen.io/LukaszJedrasiak/pen/dyKKNOV
Fetching method by Jad: https://codepen.io/LukaszJedrasiak/pen/dyKLWOX

Another example by Jad:
```js
const getChapters = () => {
    // TODO
    fetch('https://jsdemo-3f387-default-rtdb.europe-west1.firebasedatabase.app/chapters/all.json')
    .then(response => response.json())
    .then(data => {
        const completed = data.filter(element => element.isCompleted);
        displayCompletedChapters(completed);
    })
}

// do NOT modify this function
function displayCompletedChapters(chapters) {
    console.log("Received", chapters);
}

// Sample usage - do not modify
getChapters();
```

## handling errors
The fetch() promise rejects for network errors. So, if the fetch request could not complete because of a network error, it will reject and the catch() callback will execute.

However, if the fetch() request completed and the server responded with an error code (such as 4xx or 5xx), then the fetch() promise won't reject.

The reasoning here is that fetch() has been completed successfully, it's just that the server returned an error.

This means that if you make a fetch request for a URL that does not exist (a 404), the fetch() promise will be fulfilled and the .then(callback) will execute as usual. The .catch(callback) will only execute if something prevented the fetch() request from completing (for example, a network failure).

**BUT - The response object contains an ok field that returns true when the response was successful (status in the 2xx range).**

```javascript
fetch(URL)
    .then(response => {
        if (!response.ok) {
            // 4xx or 5xx error
            throw new Error("API issues.");
        }
        return response.json();
    })
    .then(data => {
        console.log(data);
    })
    .catch(error => {
        console.error(error);
    });
```

The `throw new Error("API issues.")` will **reject** the promise, so, the code stops running the current `.then(callback)` and then jumps to the `.catch(callback)`.

Full Jad demo
```js
const getChapters = () => {
    fetch("https://jsdemo-3f387-default-rtdb.europe-west1.firebasedatabase.app/chapters/all.json")
        .then(response => {
            if (!response.ok) {
                throw new Error("API issues.");
            }
            return response.json();
        })
        .then(data => {
            console.log(data); // visualize it
            const completedChapters = data.filter(chapter => chapter.isCompleted);
            displayCompletedChapters(completedChapters);
        })
        .catch(error => console.error(error));
}

// do NOT modify this function
function displayCompletedChapters(chapters) {
    console.log("Received", chapters);
}

// Sample usage - do not modify
getChapters();

```

## fetch methods
-   GET: _read_ data
-   POST: _create_ data
-   PUT: _update_ data
-   DELETE: _delete_ data

Requests made with method **PUT**, **POST**, or **DELETE** can have an extra field called `body`. The body can contain any information that you want to send with the request. However, requests made with **GET** are not allowed to have a `body`.

`fetch` boilerplate:
```javascript
fetch(URL, {
    method: "POST", // or PUT or DELETE
    //sample headers:
    headers: {
	    "Content-Type": "application/json"
    } 
    body: JSON.stringify({
        key1: 'value1', // replace with key/value based on documentation
        key2: 'value2', // same as above (if needed)
    })
})
.then(response => response.json())
.then(data => {
    console.log(data); // read server response
})
.catch(error => {
    console.error(error);
});
```

