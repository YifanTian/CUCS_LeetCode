
#### 560. Subarray Sum Equals K  (Medium) ####

Given an array of integers and an integer k, you need to find the total number of continuous subarrays whose sum equals to k. 

Example 1:
Input:nums = [1,1,1], k = 2

Output: 2

Note:
The length of the array is in range [1, 20,000].
The range of numbers in the array is [-1000, 1000] and the range of the integer k is [-1e7, 1e7].




```python
def subarraySum(nums, k):
    """
    :type nums: List[int]
    :type k: int
    :rtype: int
    """
    subsum_dict = dict()
    subsum = 0
    res = 0
    subsum_dict[0] = 1
    for i in range(len(nums)):
        subsum += nums[i]
        if subsum - k in subsum_dict:
            res += subsum_dict[subsum - k]
        if subsum in subsum_dict:
            subsum_dict[subsum] += 1
        else:
            subsum_dict[subsum] = 1
    return res
```


```python
subarraySum([1,1,1],2)
```




    2




```python

```
