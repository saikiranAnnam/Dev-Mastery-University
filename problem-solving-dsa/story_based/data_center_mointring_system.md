You are working on a data center monitoring system.

You receive a list of request loads per second:

loads = [ ... ]

Due to system constraints, the data center can only handle a maximum total load of k at any time.

Your task is to find the longest continuous time window where the total load does not exceed k.


so this is how i start looking at the problem, 

we are getting requests, we have the load. 

here,
lets take all the load values, are non-negative and the k is also not negative. 

total elements inside the load should not exceed k. 

example: 
loads = [1, 2, 1, 0, 1, 1, 0]
k = 4
output : 5 

[2, 1, 0, 1]  -> sum = 4, length = 4
[1, 2, 1, 0]  -> sum = 4, length = 4
[1, 0, 1, 1, 0] -> sum = 3, length = 5

```python
class Solution:
    def longestValidLoadWindow(self, loads: List[int], k:int) -> int:
        n = len(loads)
        max_length = 0
        window_sum = 0 
        window_len = 0
        left = 0

        for right in range(0,n):
            window_sum += loads[right]

            while window_sum > k:
                window_sum -= loads[left]
                left += 1

            max_length = max(max_length, (right - left + 1))
        
        return max_length
```




