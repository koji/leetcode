Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word (last word means the last appearing word if we loop from left to right) in the string.

If the last word does not exist, return 0.

Note: A word is defined as a maximal substring consisting of non-space characters only.

Example:

Input: "Hello World"
Output: 5


```python
def lengthOfLastWord(self, s: str) -> int:
        if len(s) ==0:
            return 0
        words = s.split()
        if len(words) ==0:
            return 0
        return len(words[-1])
```


```
Runtime: 24 ms, faster than 94.87% of Python3 online submissions for Length of Last Word.
Memory Usage: 14.1 MB, less than 100.00% of Python3 online submissions for Length of Last Word.
```
