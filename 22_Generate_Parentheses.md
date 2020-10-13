Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

 

Example 1:

Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
Example 2:

Input: n = 1
Output: ["()"]
 

Constraints:

1 <= n <= 8



```python
def generateParenthesis(self, n: int) -> List[str]:
        return self.helper(n, n, '', [])
    
def helper(self, openB, closeB, path, result):
    if openB == 0 and closeB == 0:
        result.append(path)

    if openB > 0:
        self.helper(openB - 1, closeB, path+'(', result)
    if closeB > openB:
        self.helper(openB, closeB - 1, path+')', result)
        
    return result
```
