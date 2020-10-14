## 434. Number of Segments in a String

You are given a string s, return the number of segments in the string. 

A segment is defined to be a contiguous sequence of non-space characters.

 

Example 1:

Input: s = "Hello, my name is John"
Output: 5
Explanation: The five segments are ["Hello,", "my", "name", "is", "John"]
Example 2:

Input: s = "Hello"
Output: 1
Example 3:

Input: s = "love live! mu'sic forever"
Output: 4
Example 4:

Input: s = ""
Output: 0





```python
def countSegments(self, s: str) -> int:
        if s is '': return 0
        return len(s.split())
```


```
Runtime: 28 ms, faster than 74.58% of Python3 online submissions for Number of Segments in a String.
Memory Usage: 14.2 MB, less than 100.00% of Python3 online submissions for Number of Segments in a String.
```
