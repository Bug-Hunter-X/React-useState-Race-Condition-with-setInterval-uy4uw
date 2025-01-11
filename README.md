# React useState Race Condition with setInterval

This repository demonstrates a common bug in React applications involving the `useState` hook and `setInterval`.  The bug arises from a race condition when updating state based on the previous state directly inside the `setInterval` callback.

## The Problem

The provided `MyComponent` uses `setInterval` to increment a counter every second. However, the update `setCount(count + 1)` can lead to inconsistent updates because the value of `count` might be stale by the time the state update is processed.

## The Solution

The solution uses the functional update form of `setCount` to address the race condition. This ensures that the counter is always updated based on the latest state value, resulting in correct increments.