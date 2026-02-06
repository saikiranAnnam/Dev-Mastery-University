### 242. Valid Anagram 

🔗 Link : https://leetcode.com/problems/valid-anagram/description/

**Problem Statement :** Given two strings s and t, return true if t is an anagram of s, and false otherwise.

**Note**: An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, using all the original letters exactly once.

Example 1:

Input: s = "anagram", t = "nagaram"

Output: true

Example 2:

Input: s = "rat", t = "car"

Output: false

Constraints:

1 <= s.length, t.length <= 5 * 10^4
s and t consist of lowercase English letters.


**Understanding :**
we have 2 strings, each string is group of characters. to check the strings are anagram, the character in strings should match. 

so, get the count from the strings compare them. 


**Approach - 1(using Counter)**
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        char_dict1 = {}
        char_dict2 = {}

        char_dict1 = Counter(s)
        char_dict2 = Counter(t)

        return char_dict1 == char_dict2
```

**Approach - 2**
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        validAnagram = True
        char_dict = {}

        for c in s:
            char_dict[c] = char_dict.get(c, 0) + 1

        for c in t:
            char_dict[c] = char_dict.get(c, 0) - 1
            if char_dict[c] < 0: 
                validAnagram = False
                
        return validAnagram
```

tc : O(n)
sc : O(1)