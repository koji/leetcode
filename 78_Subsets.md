## 78. Subsets


Given a set of distinct integers, nums, return all possible subsets (the power set).

Note: The solution set must not contain duplicate subsets.

Example:

Input: nums = [1,2,3]
Output:
[
  [3],
  [1],
  [2],
  [1,2,3],
  [1,3],
  [2,3],
  [1,2],
  []
]


```python
def subsets(self, nums: List[int]) -> List[List[int]]:
        
        result = []
        def traverse(build, index):
            if len(nums) == index:
                result.append(build)
                return
            
            traverse(build, index+1)
            traverse(build+[nums[index]], index+1)
            
            
        traverse([], 0)
        return result
```


```
Runtime: 32 ms, faster than 77.43% of Python3 online submissions for Subsets.
Memory Usage: 14.3 MB, less than 100.00% of Python3 online submissions for Subsets.
```
