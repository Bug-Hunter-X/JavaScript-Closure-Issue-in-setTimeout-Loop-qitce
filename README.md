# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The expected behavior is to print numbers 0 through 9 sequentially with a one-second delay.  However, due to the way closures work in JavaScript, the code incorrectly prints '10' ten times.

## The Problem

The issue stems from the fact that the `setTimeout` callback function doesn't capture the value of `i` at the time it's created within each iteration of the loop. Instead, it captures a reference to the variable `i`. By the time `setTimeout` finally executes the callback, the loop has already completed, and `i` holds its final value of 10.

## The Solution

The solution involves creating a new scope for each iteration using an immediately invoked function expression (IIFE) or using `let` within the loop.  This ensures that each callback function has its own copy of the current value of `i`.

## How to Run

1. Clone this repository.
2. Open `bug.js` to see the buggy code.
3. Open `bugSolution.js` to see the corrected code.
4. Open the files in your browser's developer console or use Node.js to execute them.