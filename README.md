# React useEffect setInterval Memory Leak

This example demonstrates a common error in React when using `setInterval` within the `useEffect` hook.  Failing to provide a cleanup function to `clearInterval` leads to memory leaks. The component continues to update the count even after it is unmounted.

## Bug
The `bug.js` file contains the erroneous code. The `setInterval` function is called, but the interval ID is not stored, and there is no way to stop the interval, leading to a memory leak.

## Solution
The `bugSolution.js` file provides the corrected code with the necessary cleanup function to prevent the memory leak.  The `clearInterval` function is called within the return of `useEffect` to ensure the interval is cleared when the component unmounts or when the dependency array changes.
