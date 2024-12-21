# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common mistake in React applications: using `setInterval` within a `useEffect` hook without properly cleaning up the interval. This leads to a memory leak as the interval continues to run even after the component unmounts.

## Bug Description
The `MyComponent` component uses `setInterval` to update the count every second.  However, the interval ID is not stored or cleaned up using `clearInterval` within the cleanup function of the `useEffect` hook.  This results in a memory leak because the interval continues to run after the component is unmounted.

## Bug Solution
The solution involves storing the interval ID in a variable and then using `clearInterval` within the cleanup function of the `useEffect` hook to stop the interval before the component is unmounted.