Given an array of integers nums.

A pair (i,j) is called good if nums[i] == nums[j] and i < j.

Return the number of good pairs.

Example 1:

Input: nums = [1,2,3,1,1,3]
Output: 4
Explanation: There are 4 good pairs (0,3), (0,4), (3,4), (2,5) 0-indexed.
Example 2:

Input: nums = [1,1,1,1]
Output: 6
Explanation: Each pair in the array are good.
Example 3:

Input: nums = [1,2,3]
Output: 0
 

Constraints:

1 <= nums.length <= 100
1 <= nums[i] <= 100

0. create a counter 
1. create a hash table: a key is number 
2. if key's value > 1 nCr r=2 and add the result to counter
3. return counter 

```python
from math import factorial
def calc_pattern(self, n):
    return factorial(n) // factorial(2) // factorial(n - 2)
    
def numIdenticalPairs(self, nums: List[int]) -> int:
    from collections import Counter
    dic = Counter(nums)
    counter = 0
    for k,v in dic.items():
        if v >1:
            counter += self.calc_pattern(v)
    return counter
```
