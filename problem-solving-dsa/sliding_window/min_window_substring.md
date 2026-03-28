# Minimum window Substring

Given two strings s and t of lengths m and n respectively, return the minimum window of s such that every character in t (including duplicates) is included in the window. If there is no such substring, return the empty string "".

The testcases will be generated such that the answer is unique.

Example:
Input: s = "ADOBECODEBANC", t = "ABC"
Output: "BANC"

Explanation: The minimum window substring "BANC" includes 'A', 'B', and 'C' from string t.

Example:
Input: s = "a", t = "a"
Output: "a"
Explanation: The entire string s is the minimum window.

Example:
Input: s = "a", t = "aa"
Output: ""
Explanation: Both 'a's from t must be included in the window.
Since the largest window of s only has one 'a', return empty string.


code: 
```python
class Solution:
    def minWindow(self, s: str, t: str) -> str:
        # s is a str, with length of m
        # t is a str, with length of n
        
        t_freq = {}
        #freqmap of t
        for c in t:
            t_freq[c] = t_freq.get(c, 0) + 1

        window = {}
        left = 0
        have = 0 # chars in the s
        need = len(t_freq) # chars in the t
        min_len = float("inf")
        res = [-1, -1] #if we dont have anything

        for right in range(len(s)):
            char = s[right]
            window[char] = window.get(char, 0) + 1

            if char in t_freq and window[char] == t_freq[char]:
                have += 1
            
            while have == need:
                if (right - left + 1) < min_len:
                    min_len = right - left + 1
                    res = [left, right]

                window[s[left]] -= 1 
                if s[left] in t_freq and window[s[left]] < t_freq[s[left]]:
                    have -= 1
                left += 1
            
        if min_len == float("inf"):
            return ""
        else:
            return s[res[0] : res[1] + 1]
```