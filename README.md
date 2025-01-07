# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug: an infinite render loop caused by an improperly used `useEffect` hook.  The `useEffect` hook, without the correct dependency array, triggers an update to the state inside the `useEffect` which leads to the component re-rendering infinitely.

## Bug Description
The `bug.js` file contains a `MyComponent` that uses the `useEffect` hook to update the `count` state. However, the dependency array `[]` is empty, meaning the effect runs after every render.  This creates a loop: the effect increments the count, causing a re-render, which triggers the effect again, and so on.

## Solution
The `bugSolution.js` file provides a corrected version of the component.  The dependency array is now `[count]`, meaning the effect only runs when the `count` state changes.  This prevents the infinite loop.