## Maximum Subarray

Given an integer array nums, find the with the largest sum, and return its sum.

Example 1:

Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: The subarray [4,-1,2,1] has the largest sum 6.

Example 2:

Input: nums = [1]
Output: 1
Explanation: The subarray [1] has the largest sum 1.


```python
def max_subarray(nums: List[int]) -> int:
    current = nums[0]
    best = nums[0]
    
    for i in range(1, len(nums)):
        current = max(nums[i], current + nums[i])
        best = max(best, current)

    return best
```

tc : O(n)