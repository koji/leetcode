## 72. Edit Distance

```
Given two strings word1 and word2, return the minimum number of operations required to convert word1 to word2.

You have the following three operations permitted on a word:

Insert a character
Delete a character
Replace a character
 

Example 1:

Input: word1 = "horse", word2 = "ros"
Output: 3
Explanation: 
horse -> rorse (replace 'h' with 'r')
rorse -> rose (remove 'r')
rose -> ros (remove 'e')
Example 2:

Input: word1 = "intention", word2 = "execution"
Output: 5
Explanation: 
intention -> inention (remove 't')
inention -> enention (replace 'i' with 'e')
enention -> exention (replace 'n' with 'x')
exention -> exection (replace 'n' with 'c')
exection -> execution (insert 'u')
 

Constraints:

0 <= word1.length, word2.length <= 500
word1 and word2 consist of lowercase English letters.

```


```python
class Solution:
    def minDistance(self, word1: str, word2: str) -> int:
        m = len(word1)
        n = len(word2)
        dp = [[float('inf')]*(n+1) for i in range(m+1)]
        # print(dp)
        dp[0][0]= 0
        
        for i in range(0, m+1):
            for j in range(0, n+1):
                if i > 0 and j>0:
                    # word1[i] == word2[j]
                    if word1[i-1] == word2[j-1]:
                        dp[i][j] = min(dp[i][j], dp[i-1][j-1])
                    else:
                        dp[i][j] = min(dp[i][j], dp[i-1][j-1]+1)


                # remove word1[i]
                if i>0:
                    dp[i][j] = min(dp[i][j], dp[i-1][j]+1)

                # remove word2[j]
                if j>0:
                    dp[i][j] = min(dp[i][j], dp[i][j-1]+1)
                
        return dp[-1][-1]
```


```
Runtime: 432 ms, faster than 5.22% of Python3 online submissions for Edit Distance.
Memory Usage: 17.8 MB, less than 41.17% of Python3 online submissions for Edit Distance.
```
