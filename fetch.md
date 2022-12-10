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