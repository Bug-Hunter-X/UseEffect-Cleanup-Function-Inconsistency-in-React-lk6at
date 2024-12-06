# React useEffect Cleanup Function Inconsistency

This repository demonstrates an uncommon bug related to the cleanup function in React's `useEffect` hook. The issue arises when the cleanup function doesn't always execute as expected, potentially leading to memory leaks or unexpected behavior.

## Bug Description
The provided `MyComponent` uses `useEffect` to log the current `count` state.  The cleanup function logs 'Cleanup!'.  In normal circumstances, the cleanup function should execute before the next effect. However, this isn't always consistent and may cause issues under certain conditions like rapid component unmounting, or when combined with other effects.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs.  The inconsistency in the execution of the cleanup function may not be immediately apparent, but can manifest under specific scenarios.

## Solution
The solution involves ensuring that the dependency array for `useEffect` is properly defined to trigger the effect only when necessary.  The count variable is now correctly included in the dependency array to only run the effect when the count changes.  This ensures that the cleanup function runs appropriately and avoids unexpected behavior.