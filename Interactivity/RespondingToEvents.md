# Intro
React lets you add event handlers to your JSX. Event handlers are your own functions that will be triggered in response to interactions like clicking, hovering, focusing form inputs, and so on.

## Understanding Events
- Like HTML DOM events, React too perform action based on user events
## 
- React events are written in camelCase syntax:

*onClick instead of onclick>*

- React event handlers are written inside curly braces:

*onClick={shoot}  instead of onClick="shoot()"*

- React :

```<button onClick={shoot}>Take the Shot!</button>```

- HTML:

```<button onclick="shoot()">Take the Shot!</button>```

Example: 
```
function Football() {
	  const shoot = () => {
	    alert("Great Shot!");
	  }

	  return (
	    <button onClick={shoot}>Take the shot!</button>
	  );
	}

	const root = ReactDOM.createRoot(document.getElementById('root'));
	root.render(<Football />);
```
## Example:
```
export default function App() {
  return (
    <Toolbar
      onPlayMovie={() => alert('Playing!')}
      onUploadImage={() => alert('Uploading!')}
    />
  );
}

function Toolbar({ onPlayMovie, onUploadImage }) {
  return (
    <div>
      <Button onClick={onPlayMovie}>
        Play Movie
      </Button>
      <Button onClick={onUploadImage}>
        Upload Image
      </Button>
    </div>
  );
}

function Button({ onClick, children }) {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
}
```
- In the above code snnipet there is a react component that renders a instance of toolbar component.

- The toolbar component recieve two props as input: onPlayMovie and onUploadImage.

- The toolbar component renders two instance on button.

- The button compoent recieves two props as input: onClick (which is the function which shows the alert message)and children (this is the content inside the button).