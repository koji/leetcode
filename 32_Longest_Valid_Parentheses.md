## 32. Longest Valid Parentheses


Given a string containing just the characters '(' and ')', find the length of the longest valid (well-formed) parentheses substring.


Example 1:

Input: s = "(()"
Output: 2
Explanation: The longest valid parentheses substring is "()".
Example 2:

Input: s = ")()())"
Output: 4
Explanation: The longest valid parentheses substring is "()()".
Example 3:

Input: s = ""
Output: 0
 

Constraints:

0 <= s.length <= 3 * 104
s[i] is '(', or ')'.


```python
def longestValidParentheses(self, s: str) -> int:
        if len(s) ==0: return 0
        stack = [-1]
        maxLen = 0
        for i in range(len(s)):
            if s[i] == '(':
                stack.append(i)
            else:
                stack.pop()
                if len(stack) == 0:
                    stack.append(i)
                else:
                    maxLen = max(i-stack[-1], maxLen)
        return maxLen
```

```
Runtime: 32 ms, faster than 99.13% of Python3 online submissions for Longest Valid Parentheses.
Memory Usage: 14.4 MB, less than 5.50% of Python3 online submissions for Longest Valid Parentheses.
```
