## State as Snapshot

- React state behaves more like sanpshot.It will not change the state variable but trigger a re-render. 

-   ```
    {
    setCount(score+1);  (score here wil be 0)
    setCount(score+1);  (score here wil be 0)
    setCount(score+1); (score here wil be 0)
    }
    ```
- So lets assume this is a component where we want to update the state 3 times.Each time you call the setcount function the score is always 0 because React waits until all code in the event handlers has run before processing your state updates. 

## Queueing a Series of State Update 

- You can fix the above issue by passing a updater function when setting state
setScore(s=>s+1).