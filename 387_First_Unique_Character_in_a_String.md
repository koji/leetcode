## 387. First Unique Character in a String


Given a string, find the first non-repeating character in it and return its index. If it doesn't exist, return -1.

Examples:

s = "leetcode"
return 0.

s = "loveleetcode"
return 2.



```python
def firstUniqChar(self, s: str) -> int:
        dic = Counter(s)
        for k, v in dic.items():
            if v == 1:
                return s.index(k)
        return -1
```


```
Runtime: 52 ms, faster than 98.59% of Python3 online submissions for First Unique Character in a String.
Memory Usage: 14.2 MB, less than 100.00% of Python3 online submissions for First Unique Character in a String.
```
