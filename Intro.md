### Intro
React is made of components
##
Components is a UI that has it own logic and appearance
##
React is a javascript function that returns markup

Component ex- 

```
function MyButton() {
    return (
      <button>I'm a button</button>
    );
}
```

Nested Component - 
```
export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}
```
Component name in react should start with capital letter like MyButton and html tag should be in lowercase
##
Displaying Data - jsx helps you put markup in javascript and {} helps you to go back to javascript where you can include other function.

```
return (
  <h1>
    {user.name}
  </h1>
);
```

### Conditional Rendering - 

```
let content;
if (isLoggedIn) {
  content = <AdminPanel />;
} else {
  content = <LoginForm />;
}
return (
  <div>
    {content}
  </div>
);
```

### Responding to Event - 
##
Below you can observe that the {handleclick} dont have () paranthesis at the end its because we just have to give function and react will call the function when user click the button.

```
function MyButton() {
  function handleClick() {
    alert('You clicked me!');
  }

  return (
    <button onClick={handleClick}>
      Click me
    </button>
  );
}
```

### Updating the screen - 
##
Usestate is react hook that allow you to use state for functional component
##
It return an array with two values : current state and a function to update it
##
Hook takes an initial state value as an argument and returns an updated state value whenever the setter function is called.

```
const [state, setState] = useState(initialValue);
```
Example - 
```function MyButton() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return (
    <button onClick={handleClick}>
      Clicked {count} times
    </button>
  );
}
```
### Hooks - 
##
Function starting with use are called hooks. "usestate" is a build in hook.
##
Hooks are more restrictive than other functions. You can only call Hooks at the top of your components (or other Hooks). If you want to use useState in a condition or a loop, extract a new component and put it there.

##
### Sharing data between component-

## 
Below you can see that when you want to share the state then we move the state upward to the parent component 

##
The parameter we passed in button function are called props

```
import { useState } from 'react';
  
  export default function MyApp() {
    const [count, setCount] = useState(0);
  
    function handleClick() {
      setCount(count + 1);
    }
  
    return (
      <div>
        <h1>Counters that update together</h1>
        <MyButton count={count} onClick={handleClick} />
        <MyButton count={count} onClick={handleClick} />
      </div>
    );
  }
  
  function MyButton({ count, onClick }) {
    return (
      <button onClick={onClick}>
        Clicked {count} times
      </button>
    );
  }
  ```







