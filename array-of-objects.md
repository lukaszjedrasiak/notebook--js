```js
const tweets = [
    {
        id: 1080777336298049537,
        message: "Hello Twitter 👋",
        created_at: "2020-01-03 11:46:00",
        sampleProperty: {
            content: "xxx"
        },
        author: {
            id: 109215315,
            firstName: "Jad",
            lastName: "Joubran",
            handle: "JoubranJad",
            nick: "JJ"
        }
    },
    {
        id: 1080777336298195435,
        message: "How do you keep track of your notes?",
        created_at: "2021-02-19 15:32:00",
        author: {
            id: 109216891,
            firstName: "Sam",
            lastName: "Green",
            handle: "SamGreen"
        }
    }
];

// log property
tweets.forEach(tweet => {
    console.log(tweet.sampleProperty?.content ?? "no entry");
})

// export authors handles
const authors = tweets.map(tweet => tweet.author.handle);
console.log("authors: " + authors.join("; "))
```