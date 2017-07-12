## Is `setState` in ReactJS Async or Sync?

**In short: it depends on how you call/trigger `setState`**

plz refer to these two awesome resources:

[setState() State Mutation Operation May Be Synchronous In ReactJS](https://www.bennadel.com/blog/2893-setstate-state-mutation-operation-may-be-synchronous-in-reactjs.htm)

[setState in reactjs is Async or Sync - StackOverflow](https://stackoverflow.com/questions/36085726/setstate-in-reactjs-is-async-or-sync)

So why it is generally asynchrnous? A short answer is for performance reason, because React wants to **batch** the changes, so that the Virtual DOM won't change everytime you `setState` runs.

update:

However, you could provide a callback function instead the state object to make `setState` run immediately:

```js
this.setState(prevState => {
  return newStateObj
})
```
