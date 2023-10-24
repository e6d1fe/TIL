# State

## Batching

Batching: The behavior in which React processes state updates after all the other codes in an event handler have finished running

```
<button onClick={() => {
  setNumber(number + 1);
  setNumber(number + 1);
  setNumber(number + 1);
}}>
```

⬆️ When you click this button, number is only incremented by `1` due to batching. But what if you want to make it increment by `3`?

```
<button onClick={() => {
  setNumber(n => n + 1);
  setNumber(n => n + 1);
  setNumber(n => n + 1);
}}>
```

⬆️ You can change the code like this. `n => n + 1`, which is passed into `setNumber`, is called an updater function. Updater functions are stored in queues and are processed during the next render.  
So if you want to update a certain state multiple times in one event, you can use updater functions like this.
