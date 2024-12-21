# React 19 useState Hook Unexpected Behavior
This repository demonstrates a subtle bug in React 19 related to the `useState` hook and complex state update functions.  The issue arises when the update function depends on the previous state but doesn't use the functional update pattern correctly, leading to unexpected behavior and stale closures.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version.

## Problem
The original code attempts to increment a count by a value that depends on the current count, but due to the asynchronous nature of state updates, the function might capture a stale value of `count`, resulting in incorrect increments.

## Solution
The solution uses the functional update form of `setCount`, ensuring that the update function always receives the most recent state value.