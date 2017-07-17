# Difference Between Lodash `merge` And `assign`

So I came across a weird bug today when I was writing my own project. Previously, I saw people use the lodash merge function to update state in Redux, so did I.

But here is where the trouble comes. Let me describe it in code:

```js
// assume this is the previous state
const originalState = { data: [3,3,3,3] }

// update the state:
let newState = _.merge({}, originalState, { date: [0,0,0] })
```

Before, I suppose the `data` in the new state should be `[0,0,0]`, but I got this:

```js
newState: { data: [0,0,0,3] }
```

The document of `merge` says:  

> Source properties that resolve to undefined are **skipped** if a destination value exists.

which means, if you new state is "smaller" than your previous state, the remaining part will still be kept when you do the updating.

That's soooo ***EVIL***!

We all know that the main difference of `merge` and `assign`, that is, `assign` is **shallow copy, override**, while `merge` is **deep copy, replicate**. But this might be a hard-to-find-part where you should pay attention. Anyway, be much more aware of its difference when you write real code.

Good luck!
