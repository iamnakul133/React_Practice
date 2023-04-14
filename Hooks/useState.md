# Inro
useState is a React Hook that lets you add a state variable to your component.

## syntax: 
> const [state, setState] = useState(initialState);

## Parameter: 
- initialState is the value you want the state to be initially.It can be of any time.This argument is ignored after the initial render.

- If you pass a function as initialState, it will be treated as an initializer function. It should be pure, should take no arguments, and should return a value of any type. React will call your initializer function when initializing the component, and store its return value as the initial state. 

## Returns: 
1. The current state
    - it holds the current value of the state
2. The Set function 
    - that lets you update the value with new value and it triggers a re-render of the component with update new value.
    - You can pass the next state directly, or a function that calculates it from the previous state (updater function).React will put your updater function in a queue and re-render your component. During the next render, React will calculate the next state by applying all of the queued updaters to the previous state.
    - The function passed to setcount can also take a callback function as an argument to perform asynchronous state updates.
    - set functions do not have a return value.
    - If the current state and new value are identical then react skip the re-rendering the component and its children.
    - React batches state updates. It updates the screen after all the event handlers have run and have called their set functions. This prevents multiple re-renders during a single event. 