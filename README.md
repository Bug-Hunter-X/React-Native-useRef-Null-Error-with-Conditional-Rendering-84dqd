# React Native useRef Null Error with Conditional Rendering

This repository demonstrates a common error encountered when using the `useRef` hook in React Native with conditionally rendered components.  The error arises from attempting to access the ref's current value before the referenced element has been mounted in the DOM.

## Problem

The provided `bug.js` file showcases a component where a Text element is only rendered if a condition (`someCondition`) is true.  The `useEffect` hook attempts to access and manipulate `myRef.current`, but this can occur before the Text element (and thus the ref) exists, leading to a null value and a potential runtime error.

## Solution

The `bugSolution.js` file presents a corrected version. The key change is introducing a conditional check within the `useEffect` to ensure `myRef.current` is not null before attempting to access it.  This safe-guards against the error by only executing the code block after the component has mounted successfully and the ref has been assigned a value.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install`.
4. Run `npx react-native run-android` or `npx react-native run-ios`.
5. Observe the console for any errors, and note how the solution avoids them.