# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications: creating an infinite loop within the `useEffect` hook.  The issue arises from improperly updating state variables that are also included in the `useEffect`'s dependency array.

## Bug Description
The `MyComponent` component uses `useState` to track a count. Inside the `useEffect` hook, the `setCount` function is used to increment the count. However, because `count` is included in the dependency array, the effect will run every time `count` changes, leading to an infinite loop.

## Solution
The solution involves correctly managing the dependency array.  If you intend to perform an action only once after the component renders, include an empty array `[]` as a dependency. If you need to track other values for conditional execution, include only those specific values within the dependency array.  Avoid including state variables directly unless you understand the potential implications.