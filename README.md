# React useEffect Dependency Array Issue

This repository demonstrates a common error in React's `useEffect` hook: incorrect usage of the dependency array, leading to unintended re-renders and potentially infinite loops. 

The `bug.js` file showcases the problematic code. The `bugSolution.js` file provides the corrected version.

## Problem
The initial code includes `count` in the dependency array of `useEffect`. While this seems intuitive, it leads to an infinite loop: every state change triggers the effect, which logs a message and the component rerenders, causing `count` to change and triggering the effect again.

## Solution
The corrected code addresses this issue.  Only include variables you need to observe in the dependency array. If you want to run an effect only once after the initial render, pass an empty array (`[]`) as the dependency array.