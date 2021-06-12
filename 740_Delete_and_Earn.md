## 740. Delete and Earn


```
Given an array nums of integers, you can perform operations on the array.

In each operation, you pick any nums[i] and delete it to earn nums[i] points. After, you must delete every element equal to nums[i] - 1 or nums[i] + 1.

You start with 0 points. Return the maximum number of points you can earn by applying such operations.

 

Example 1:

Input: nums = [3,4,2]
Output: 6
Explanation: Delete 4 to earn 4 points, consequently 3 is also deleted.
Then, delete 2 to earn 2 points.
6 total points are earned.
Example 2:

Input: nums = [2,2,3,3,3,4]
Output: 9
Explanation: Delete 3 to earn 3 points, deleting both 2's and the 4.
Then, delete 3 again to earn 3 points, and 3 again to earn 3 points.
9 total points are earned.
 

Constraints:

1 <= nums.length <= 2 * 104
1 <= nums[i] <= 104
```


```python
class Solution:
    def deleteAndEarn(self, nums: List[int]) -> int:
        
    
    # [2,5,5,6,6,4,4,10,10,10]
    #  1  2. 3. 4. 5.  6.  7. 8. 9  10
    # [0, 2, 0, 8, 10, 12, 0, 0, 0, 30]
    # convert array for house rubber
  
        # convert arr for house robber
        max_val = max(nums)
        arr = [0] * max_val
        
        for num in nums:
            arr[num-1] += num
                
        size = len(arr)
        if size == 1:
            return arr[0]
        dp = [0] * (size)
        dp[0] = arr[0]
        dp[1] = max(arr[0], arr[1])
        
        for i in range(2, size):
            dp[i] = max(dp[i-1], dp[i-2] + arr[i])
        
        return dp[-1]
```


```
Runtime: 56 ms, faster than 69.52% of Python3 online submissions for Delete and Earn.
Memory Usage: 14.7 MB, less than 28.38% of Python3 online submissions for Delete and Earn.
```
