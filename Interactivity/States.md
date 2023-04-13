# Intro
- component need to change what's on the screen as a result of of an intereaction.
- Component need to remember things: the current input value, the current image, the shopping cart
- In React, this kind of component - specific memory is called state. 
- The 'useState' Hook lets you declare a state variable. It takes the initial state and return a pair of values: the current state, and a state setter function that lets you update it. 

## Syntax: 
```
const [index, setIndex] = useState(0); 
const [showMore, setShowMore] = useState(false);

Here is the example of how to increment the counter using state and onClick: 

import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  function increment() {
    setCount(count + 1);
  }

  function decrement() {
    setCount(count - 1);
  }

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}

export default Counter;
```