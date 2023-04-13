# Intro
Any screen update in a React app happens in three steps:
1. Trigger a render
2. Rendering the component
3. Committing to the DOM

### 1. Trigger a render
There are two reason for a component to render
- Initial render
    - when the app starts, you need to trigger the initial render. This is done by calling the createRoot with the target DOM node, then calling its render method on your component 
    - ```
        import Image from './Image.js';
        import { createRoot } from 'react-dom/client';

        const root = createRoot(document.getElementById('root'))
        root.render(<Image />);
        ```
- The component state has been updated
    - Re-Render when state updates: Once you have initially rendered, you can trigger furthur renders by updating its state with the set function.

### 2. Rendering the Component
- After triggering the render the react call the component to figure out what to display on the screen

- "Rendering" is react calling your component 

    - At initial render react will call the root component 
    * Now at subsequent render react will call the component whose state update triggered the render.

- If component return some other component, React will render that component next, so on. 

### 3. Commiting to DOM
- After Rendering, React will modify the DOM

    - Upon initial render, React will use the DOM Api(appendChild()) to put all the DOM nodes it has created on screen.
    * For re-renders, it will apply minimum operation to make the DOM match the latest rendering output.

- React only changes the DOM nodes if there’s a difference between renders. 

