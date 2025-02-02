# React useEffect Hook: Missing Dependency Bug

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include all dependencies in the dependency array.  This can lead to unexpected behavior, including infinite render loops and incorrect state updates.

## Bug Description:

The `MyComponent` function uses `useEffect` to log the current count to the console.  However, the initial implementation omits `count` from the dependency array. This causes the effect to run on every render, creating an infinite loop because setting the state triggers a re-render, which in turn triggers the effect again.

## Solution:

The solution involves adding `count` to the dependency array.  Now, the effect only runs when the value of `count` changes, resolving the infinite loop and ensuring the component behaves as expected.