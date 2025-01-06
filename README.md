# React State Update Bug: Direct Mutation

This repository demonstrates a common bug in React applications: directly mutating the state variable instead of using the `setState` function (or its functional equivalent `setCount` in this case).  This leads to the component not re-rendering correctly because React's change detection mechanism relies on state updates happening through its designated methods.

## Bug Description
The `handleClick` function in `bug.js` attempts to increment the `count` state variable directly using the assignment operator (`=`).  This bypasses React's state management system, causing the UI not to reflect the actual changes in state.

## Solution
The `bugSolution.js` file shows the correct way to update state: using the `setCount` function with a functional update, ensuring that React's internal mechanisms update the component effectively.  The functional update (`prevCount => prevCount + 1`) also handles potential race conditions better than directly assigning a new value.