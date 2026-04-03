# Longest Consecutive Sequence

Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

You must write an algorithm that runs in O(n) time.

Example 1:

Input: nums = [100,4,200,1,3,2]
Output: 4
Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.

Example 2:

Input: nums = [0,3,7,2,5,8,4,6,0,1]
Output: 9

Example 3:

Input: nums = [1,0,1,2]
Output: 3


```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        # consecutive sequence
        # return max length 
        # unsorted and random

        # basic appporach
        # sort the elements in an array, check there consecutive(condition) update the length. 
        # Note: consecutive means num2 - num1 = 1 (where num2 >> num1)
        # t.c => O(n log n) 

        # better apporach
        # go through the array if we got n1, we need to check if there is any element present in the array with n1-1 or n1+1. 
        # if we have the element we need push n1, n1-1 or n1+1 or both if present into a set
        # we need to check if the n1-1 exists skip checking
        # we need to check if n1-1 doesnt exists 
        # and then we need to check for the n1-1 or n1 + 1 
        # update the length in each loop run 
        # tc : O(n) and sc: O(k) k is the max length of the consecutive elements in seqeuence. 
        num_set = set(nums)
        longest = 0

        for num in num_set:
            if num - 1 not in num_set:
                length = 1
                current = num

                while current + 1 in num_set:
                    length += 1
                    current += 1

                longest = max(longest, length)

        return longest
```

q1.Why do we check if num - 1 not in set?
We check num - 1 not in set to identify whether the current number is the start of a sequence. If num - 1 exists, then this number is already part of a sequence and starting from it would repeat work.

q2. What happens if we remove that condition? if num - 1 not in set
Without that condition, we would expand from every number, including numbers in the middle of a sequence. That causes the same streak to be traversed many times. For a long consecutive run, this repeated expansion can make the solution degrade toward O(n²).

q3. Why do we iterate over set(nums) instead of nums?
We iterate over set(nums) instead of nums to avoid duplicate processing and keep the logic clean. The set stores only unique values, and it also supports average O(1) membership checks, which is what makes the sequence expansion efficient.

