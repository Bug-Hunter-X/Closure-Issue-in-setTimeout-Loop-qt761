# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The expected output is a sequence of numbers from 0 to 9, but due to closure, the actual output is all 10s.  The solution showcases how to properly handle closures in this scenario using an immediately invoked function expression (IIFE).

## Bug
The bug lies in how the variable `i` is accessed within the `setTimeout` callback function.  By the time `setTimeout` finally executes, the loop has already completed, and the value of `i` is its final value of 10.

## Solution
The solution uses an IIFE to create a new scope for each iteration of the loop.  This ensures that each callback function has its own copy of the `i` value at the time the `setTimeout` was called.