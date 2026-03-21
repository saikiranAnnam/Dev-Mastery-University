# Maximum sum of the subarray of size k

```python
nums = [2,1,5,1,3,2]
k = 3
```

Subarrays of size 3:
[2,1,5] = 8
[1,5,1] = 7
[5,1,3] = 9
[1,3,2] = 6
Answer = 9

idea:
0. size is fixed here. (`hint: fixed size sliding window`)
1. keep adding numbers in the `right` part of the window.
2. remove the numbers in the `left` part of the window, to maintain the fixed size of the window.
3. when the size of the window becomes 'k', update the answer.

code: 
```python
def fixed_window(nums, k):
    left = 0 
    window_sum = 0
    best = float('-inf') # set the max to minus inifity.

    for right in range(len(nums)):
        window_sum += nums[right] # add elements in the right

        if right - left + 1 > k: # check the window is valid
            window_sum -= nums[left] # remove the elements in the left
            left += 1
        
        if right - left + 1 == k: #update the answer, when the window size is valid
            best = max(best, window_sum)

    return best
```

tc: O(n)