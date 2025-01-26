# Uncommon React useEffect Bug: Unexpected Multiple Rerenders

This repository demonstrates a subtle bug related to the React `useEffect` hook. The effect runs more frequently than anticipated, leading to performance issues and unexpected behavior.  The root cause is a misunderstanding of how state updates within an effect trigger additional renders.

## Bug Description

The provided `MyComponent` uses `useEffect` to log the current `count` after every render.  Due to the synchronous nature of state updates, the effect runs multiple times, resulting in unnecessary console logs and potential performance degradation.  This is especially problematic in complex components with multiple state variables and effects.

## Solution

The solution involves using the functional form of the `setState` method provided by the `useState` hook.  This allows for updating the state based on its previous value asynchronously, preventing further renders within the same effect's execution.