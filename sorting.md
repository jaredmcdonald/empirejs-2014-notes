# Sorting Algorithms in JavaScript

## 3 important factors when it comes to sorting

1. stability

   stable sorts maintain the relative order of items with equal "values"

2. runtime analysis

   - gives a variable to compare algorithms
   - represents complexity in terms of time
   - `O(x) -> x` is number of operations, function of `n` items
   - Big-O, Big-Omega, Big-Theta

   Runtime analysis should not be the sole determinant of what the best sorting algorithm is. Maybe your algorithm takes up too much space (it created too many temp arrays, etc.)

We'd like to shoot for logarithmic runtime, and to do this, we need to implement recursion

3. The algorithm's implementation...


## 3 kinds of sorting algorithms we'll look at today

1. insertion sort

  - nest for loops and compare items to the one next to them; swap
  - worst case scenario is `O(n^2)`
  - it's stable
  - good for small amount of data and not much space
  - check in loop condition

2. bubble sort

  - similar to insertion sort except checking inside body of loop
  - it's not very good: goes through every item every time
  - worst case `O(n^2)`
  - not stable

3. merge sort

  - logarithmic order: `O(n log n)`
  - 'divide and conquer' - multi-branched recursion
  - don't do it in the browser if you're working with tons of data
  - fast and stable
