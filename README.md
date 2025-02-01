# React setInterval useEffect Memory Leak
This repository demonstrates a common mistake in React applications: using `setInterval` within the `useEffect` hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it fails to include a cleanup function in the `useEffect` hook to clear the interval when the component unmounts. This means the interval continues to run even after the component is removed from the DOM, leading to a memory leak.

## Solution
The `bugSolution.js` file provides the corrected code.  It uses the return value of `useEffect` to define a cleanup function that clears the interval when the component is unmounted.  This prevents the memory leak.