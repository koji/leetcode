## 46. Permutations

Given a collection of distinct integers, return all possible permutations.

Example:

Input: [1,2,3]
Output:
[
  [1,2,3],
  [1,3,2],
  [2,1,3],
  [2,3,1],
  [3,1,2],
  [3,2,1]
]

```python
def permute(self, nums: List[int]) -> List[List[int]]:
        result = []
        if len(nums) ==0: return result

        def gen_pattern(build, index):
            if len(nums) == index:
                result.append(build)
                return
            
            for num in nums:
                if not num in build: 
                    gen_pattern(build+[num], index+1)
        
        gen_pattern([], 0)
        return result
```


```
Runtime: 36 ms, faster than 86.09% of Python3 online submissions for Permutations.
Memory Usage: 14.3 MB, less than 100.00% of Python3 online submissions for Permutations.
```
