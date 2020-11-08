## 77. Combinations

Given two integers n and k, return all possible combinations of k numbers out of 1 ... n.

You may return the answer in any order.

 

Example 1:

Input: n = 4, k = 2
Output:
[
  [2,4],
  [3,4],
  [2,3],
  [1,2],
  [1,3],
  [1,4],
]
Example 2:

Input: n = 1, k = 1
Output: [[1]]
 

Constraints:

1 <= n <= 20
1 <= k <= n

```python
def combine(self, n: int, k: int) -> List[List[int]]:
        def gen_pattern(nums, k):
            if k == 0:
                return [[]]
            if k == 1:
                return [[num] for num in nums]
            
            res = []
            for i in range(len(nums)):
                perms = gen_pattern(nums[i+1:], k-1)
                for p in perms:
                    res.append([nums[i]] + p)        
            return res
        
        nums = list(range(1, n+1))
        res = gen_pattern(nums, k)
        return res
```


```
Runtime: 556 ms, faster than 37.57% of Python3 online submissions for Combinations.
Memory Usage: 16.2 MB, less than 33.85% of Python3 online submissions for Combinations.
```
