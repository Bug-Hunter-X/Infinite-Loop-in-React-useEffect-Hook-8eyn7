# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The `useEffect` hook, without a dependency array, runs after every render, potentially creating an infinite loop if it modifies state that triggers a re-render.  This example shows the problematic code and its solution.

## Bug
The `bug.js` file contains a `useEffect` hook that logs the current count to the console after every render.  This leads to an infinite loop because the change in the console output technically causes a re-render, triggering the useEffect infinitely. 

## Solution
The `bugSolution.js` file provides a corrected version.  A dependency array `[count]` is added to the `useEffect` hook. This ensures that the effect only runs when the `count` variable changes. This prevents the infinite loop.