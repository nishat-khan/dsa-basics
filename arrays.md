# Arrays

## Question 1: Find the Maximum Subarray Sum

**Problem Statement:**

Given an array of integers, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

**Solution:**

```python
def max_subarray_sum(nums):
    max_sum = current_sum = nums[0]
    for num in nums[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum
