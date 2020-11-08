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
        result = []
        def gen_pattern(build, index):
            if len(build) ==k:
                result.append(build)
                return
            
            for i in range(index+1, n+1):
                gen_pattern(build+[i], i)
                
        gen_pattern([], 0)
        return result
```


```
Runtime: 544 ms, faster than 43.06% of Python3 online submissions for Combinations.
Memory Usage: 15.6 MB, less than 33.85% of Python3 online submissions for Combinations.
```
