## 231. Power of Two

Given an integer n, write a function to determine if it is a power of two.

 

Example 1:

Input: n = 1
Output: true
Explanation: 20 = 1
Example 2:

Input: n = 16
Output: true
Explanation: 24 = 16
Example 3:

Input: n = 3
Output: false
Example 4:

Input: n = 4
Output: true
Example 5:

Input: n = 5
Output: false
 

Constraints:

-231 <= n <= 231 - 1

```python
def isPowerOfTwo(self, n: int) -> bool:
        # return n > 0 and n == n & -n
        if not n or n < 1: return False
        return n == n & (-n)
```

```
Runtime: 24 ms, faster than 95.06% of Python3 online submissions for Power of Two.
Memory Usage: 14.1 MB, less than 99.94% of Python3 online submissions for Power of Two.
```
