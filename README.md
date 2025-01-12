# React setInterval Memory Leak

This repository demonstrates a common error in React components: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks and unexpected behavior.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it's missing a cleanup function within `useEffect` to stop the interval when the component unmounts. This causes the interval to continue running even after the component is removed from the DOM, leading to a memory leak.

## Solution
The `bugSolution.js` file shows the corrected code.  It includes a cleanup function that uses `clearInterval` to stop the interval before the component unmounts, preventing the memory leak.

## How to reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install`.
4. Run `npm start`.
5. Observe the counter.  Then, navigate away from the page; the interval will continue running in the background.
