# LEETCODE-Array-2134
To understand the solution and dry run the given code, let's break down the logic step-by-step with an example. The problem aims to find the minimum number of swaps required to group all 1s together in a circular array.

## Code Explanation
The given code works as follows:

1. **Initialization**:
   - `n` is the length of the input array `nums`.
   - `k` is the total number of 1s in the array `nums`.
   - `ones` counts the number of 1s in the current window of size `k`.
   - `maxOnes` keeps track of the maximum number of 1s found in any window of size `k`.

2. **Sliding Window**:
   - The loop runs from 0 to `2*n-1` to simulate the circular array behavior.
   - When the window size exceeds `k`, it reduces the count of `ones` by checking the element which is moving out of the window.
   - The count of `ones` is increased by 1 if the current element is 1.
   - It updates `maxOnes` to keep track of the maximum number of 1s found in any window of size `k`.

3. **Result Calculation**:
   - The minimum number of swaps required is calculated as `k - maxOnes`.

### Dry Run with Example
Consider the input array `nums = [1, 0, 1, 0, 1]`.

1. **Initialization**:
   - `n = 5`
   - `k = 3` (there are three 1s in the array)
   - `ones = 0`
   - `maxOnes = 0`

2. **Sliding Window**:
   - Loop from `i = 0` to `i = 9` (0 to `2*n - 1`)

   | i   | (i-k)%n | nums[(i-k)%n] | nums[i%n] | ones | maxOnes |
   |-----|---------|---------------|-----------|------|---------|
   | 0   | -       | -             | 1         | 1    | 1       |
   | 1   | -       | -             | 0         | 1    | 1       |
   | 2   | -       | -             | 1         | 2    | 2       |
   | 3   | 0       | 1             | 0         | 1    | 2       |
   | 4   | 1       | 0             | 1         | 2    | 2       |
   | 5   | 2       | 1             | 1         | 2    | 2       |
   | 6   | 3       | 0             | 0         | 2    | 2       |
   | 7   | 4       | 1             | 1         | 2    | 2       |
   | 8   | 0       | 1             | 0         | 1    | 2       |
   | 9   | 1       | 0             | 1         | 2    | 2       |

3. **Result Calculation**:
   - `k - maxOnes = 3 - 2 = 1`

Therefore, the minimum number of swaps required to group all 1s together is `1`.

This detailed dry run confirms that the code logic is correctly implemented to solve the problem.
