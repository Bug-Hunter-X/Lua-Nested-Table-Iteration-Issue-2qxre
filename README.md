# Lua Nested Table Iteration Bug

This repository demonstrates a subtle bug related to nested table iteration in Lua.  The `pairs` iterator can behave unexpectedly when the table being iterated over is modified during the iteration process, potentially leading to elements being missed.

The `bug.lua` file contains the problematic code. The `bugSolution.lua` provides a corrected version. 

## Bug Description
The original code recursively iterates through a nested table using `pairs`.  However, if the table structure is changed within the iteration (though this example doesn't directly modify, the recursive nature is the problematic point), the iterator's behavior is not guaranteed, leading to skipped elements.

## Solution
The solution uses a copy of the table to iterate over, ensuring that the original table structure remains unchanged throughout the iteration process.