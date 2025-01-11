# React useEffect Bug: Unexpected Rerenders with Empty Dependency Array

This repository demonstrates a subtle bug in React 18 and 19 where a `useEffect` hook with an empty dependency array still rerenders on every render in certain scenarios. This is usually unexpected and can lead to performance issues.

## Problem

The `useEffect` hook in the provided `bug.js` file is intended to run only once after the initial render. However, due to an interaction with other parts of the application (not shown here), or due to certain optimizations performed by React, it rerenders on every render.

## Solution

The solution in `bugSolution.js` addresses this by using the `useRef` hook to detect changes in a value and trigger the `useEffect` only when that value changes.