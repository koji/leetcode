## 152. Maximum Product Subarray


```
Given an integer array nums, find a contiguous non-empty subarray within the array that has the largest product, and return the product.

It is guaranteed that the answer will fit in a 32-bit integer.

A subarray is a contiguous subsequence of the array.

 

Example 1:

Input: nums = [2,3,-2,4]
Output: 6
Explanation: [2,3] has the largest product 6.
Example 2:

Input: nums = [-2,0,-1]
Output: 0
Explanation: The result cannot be 2, because [-2,-1] is not a subarray.
 

Constraints:

1 <= nums.length <= 2 * 104
-10 <= nums[i] <= 10
The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

```


```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        # Kadane's Algorithm
        max_cur = nums[0]
        max_global = nums[0]
        min_cur = nums[0]
        
        for i in range(1, len(nums)):
            prev_max_cur = max_cur
            max_cur = max(nums[i], max(max_cur * nums[i], min_cur * nums[i]))
            min_cur = min(nums[i], min(prev_max_cur * nums[i], min_cur*nums[i]))
            max_global = max(max_global, max_cur)
            
        
        return max_global
```


```
Runtime: 44 ms, faster than 98.65% of Python3 online submissions for Maximum Product Subarray.
Memory Usage: 14.3 MB, less than 83.87% of Python3 online submissions for Maximum Product Subarray.
```
