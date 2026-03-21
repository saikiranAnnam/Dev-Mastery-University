# Longest substring without repeating characters

```python
s = "abcabcbb"
```
Answer = 3 because "abc"

Idea: 
0. window is no fixed. ( hint: dynamic sliding window)
1. add more items into the right, until the duplicate or the value is already seen.
2. if the value is already seen, update the left pointer + 1. 

Code: 
```python
def longest_substring(srting: s) -> int:
    left = 0
    best = 0
    seen = set()

    for right in range(len(s)):
        while s[right] in seen:
            seen.remove(s[left])
            left +=1
        
        seen.add(s[right])
        best = max(best, right - left + 1)
    
    return best
```

tc : O(n)
sc : O(k) [k: here is the unique number of values in the string] -- constant
