Write a function that takes a string as input and reverse only the vowels of a string.

Example 1:

Input: "hello"
Output: "holle"
Example 2:

Input: "leetcode"
Output: "leotcede"
Note:
The vowels does not include the letter "y".





```python
def reverseVowels(self, s: str) -> str:
        left = 0
        right = len(s)-1
        s = list(s)
        v = ['a','e','i','o','u','A','E','I','O','U']
        
        while left<right:
            if s[left] not in v:
                left +=1
            if s[right] not in v:
                right -= 1
                
            if s[left] in v and s[right] in v:
                    s[left], s[right] = s[right], s[left]
                    left +=1
                    right -=1
        
        return ''.join(s)
```

```
Runtime: 60 ms, faster than 60.22% of Python3 online submissions for Reverse Vowels of a String.
Memory Usage: 14.9 MB, less than 7.08% of Python3 online submissions for Reverse Vowels of a String.
```
