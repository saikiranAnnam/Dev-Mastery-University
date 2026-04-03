# Valid Palindrome

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

 

Example 1:

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

Example 3:

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.






```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        start = 0
        end = len(s) - 1

        while start < end:
            # check if the s[start] is alphaNum
            while start < end and not s[start].isalnum():
                start+=1
            
            # check if the s[end] is alphaNum
            while start < end and not s[end].isalnum():
                end-=1

            if s[start].lower() != s[end].lower(): 
                return False
                
            start+=1
            end-=1
        
        return True
```
tc : O(n)
sc : O(1)



with pre-processing(regex)
```python
import re

class Solution:
    def isPalindrome(self, s: str) -> bool:
        # pre-processing
        # clean up the string
        # remove the extra spaces and convert into all the uppercases

        s = re.sub("[^a-zA-Z0-9]", "", s).lower()

        start = 0
        end = len(s) - 1

        while start <= end:
            if s[start] != s[end]: 
                return False
            start+=1
            end-=1
        
        return True
```