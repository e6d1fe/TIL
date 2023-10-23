# Render and Commit

## The Process of React Requesting & Serving UI

1. Triggering a render
2. Rendering the component
3. Committing to the DOM

### 1. Triggering a render

A render is triggered if 1️⃣ it's the component's initial render or if 2️⃣ the component is being re-rendered due to an update.

### 2. Rendering the component

In the first case(initial render of component), React calls the root component. In the second case(re-render), React calls the function component that was triggered by an update.

### 3. Committing to the DOM

In the first case, React uses `appendChild()` to add all of the created DOM nodes. In the second case, React calculates the minimal necessary operations & updates the DOM. ("minimal" necessary operations because it does not change the DOM nodes if there aren't any differences)
