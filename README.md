# Unpredictable Table Iteration in Recursive Lua Function

This repository demonstrates a potential issue with Lua's `pairs` iterator when used in recursive functions that modify the table during iteration.  The `pairs` iterator does not guarantee a specific order of traversal, and changes to the table structure during iteration can lead to unexpected and unpredictable results.

## Problem
The provided `foo` function recursively iterates through a nested table.  If the table's structure is modified during iteration, the `pairs` iterator's behavior becomes undefined. This leads to inconsistent output.

## Solution
The solution involves using a different method of iteration that provides more predictable behavior.  One alternative is to manually iterate over the keys in sorted order or using a copy of the table.