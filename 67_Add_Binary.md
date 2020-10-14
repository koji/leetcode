Given two binary strings, return their sum (also a binary string).

The input strings are both non-empty and contains only characters 1 or 0.

Example 1:

Input: a = "11", b = "1"
Output: "100"
Example 2:

Input: a = "1010", b = "1011"
Output: "10101"
 

Constraints:

Each string consists only of '0' or '1' characters.
1 <= a.length, b.length <= 10^4
Each string is either "0" or doesn't contain any leading zero.




```python
def addBinary(self, a: str, b: str) -> str:
        return str(bin(int(a,2) + int(b,2)))[2:]
```

```
Runtime: 16 ms, faster than 99.89% of Python3 online submissions for Add Binary.
Memory Usage: 14 MB, less than 99.99% of Python3 online submissions for Add Binary.
```
