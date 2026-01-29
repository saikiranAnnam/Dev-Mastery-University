## 217. Contains Duplciate

🔗 Link : https://leetcode.com/problems/contains-duplicate/description/

**Problem Statement :** Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.


Example 1:

Input: nums = [1,2,3,1]

Output: true

Explanation:

The element 1 occurs at the indices 0 and 3.

Example 2:

Input: nums = [1,2,3,4]

Output: false

Explanation:

All elements are distinct.

Example 3:

Input: nums = [1,1,1,3,3,4,3,2,4,2]

Output: true

 
Constraints:
    1 <= nums.length <= 10^5
    -10^9 <= nums[i] <= 10^9


**Understanding :**
an array is given we need to find the array contain any duplicate items. 

true -- just return true

false -- if all the items are unique. 

the constraints for this problem algorithm should be designed based around O(nlogn)

**Basic Approach :**

in the array, keep one pointer on the first element and second pointer should be placed next to it and iterate.

'''python
class Solution : 

    def containDuplicate(self, nums: List[int]) -> bool:
        n = len(nums)
        if n == 0:
            return False
        for i in range(n):
            for j in range(i+1, n):
                if nums[i] == nums [j] :
                    return True
        
        return False
'''

Tc: O(n^2)
Sc : constant

**Better Apporach**
sort the array, and just check the adjacent elements. 

'''python
class Solution : 
    def containsDuplicate(self, nums: List[nums]) -> bool: 
    nums.sort()
    n = len(nums)

    for i in range(n-1):
        if nums[i] == nums [i+1]:
            return True
    
    return False
'''
Tc : O(nlogn + c) => O(nlogn)
sc : constant 

**optimal apporach**
create a hashMap, with the items in the list. the main use of the hashmap it only store all the unqiue values in it, cant have duplicates in it. 

'''python
class Solution:
    def containsDuplicate(self, nums : List[int]) -> bool: 
        my_set = set(nums)
        if len(nums) != len(my_set):
            return True 
        return False
'''

tc : O(n)
sc : O(m) [m, the size of the hashMap]