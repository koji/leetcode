## 1419. Minimum Number of Frogs Croaking

```
Given the string croakOfFrogs, which represents a combination of the string "croak" from different frogs, that is, multiple frogs can croak at the same time, so multiple “croak” are mixed. Return the minimum number of different frogs to finish all the croak in the given string.

A valid "croak" means a frog is printing 5 letters ‘c’, ’r’, ’o’, ’a’, ’k’ sequentially. The frogs have to print all five letters to finish a croak. If the given string is not a combination of valid "croak" return -1.

 

Example 1:

Input: croakOfFrogs = "croakcroak"
Output: 1 
Explanation: One frog yelling "croak" twice.
Example 2:

Input: croakOfFrogs = "crcoakroak"
Output: 2 
Explanation: The minimum number of frogs is two. 
The first frog could yell "crcoakroak".
The second frog could yell later "crcoakroak".
Example 3:

Input: croakOfFrogs = "croakcrook"
Output: -1
Explanation: The given string is an invalid combination of "croak" from different frogs.
Example 4:

Input: croakOfFrogs = "croakcroa"
Output: -1
 

Constraints:

1 <= croakOfFrogs.length <= 10^5
All characters in the string are: 'c', 'r', 'o', 'a' or 'k'.
```


```python
class Solution:
    def minNumberOfFrogs(self, croakOfFrogs: str) -> int:
        
        if croakOfFrogs[0] != 'c' or croakOfFrogs[-1] != 'k':
            return -1
                
        total_frogs = 0
        no_of_frogs_croaking = 0
        
        dic = {'c': 0, 'r':0, 'o':0, 'a': 0, 'k': 0}
        
        for c in croakOfFrogs:
            
            if c not in dic:
                return -1
            
            if c == 'c':
                no_of_frogs_croaking +=1
                dic[c] += 1
                total_frogs = max(total_frogs, no_of_frogs_croaking)
                
            elif c == 'k':
                for char in 'croa':
                    dic[char] -= 1
                no_of_frogs_croaking -=1                
            else:
                dic[c] +=1
                        
        if no_of_frogs_croaking == 0 and list(dic.values()) == [0,0,0,0,0]:
            return total_frogs
        
        else:
            return -1
```


```
Runtime: 156 ms, faster than 87.04% of Python3 online submissions for Minimum Number of Frogs Croaking.
Memory Usage: 15 MB, less than 39.20% of Python3 online submissions for Minimum Number of Frogs Croaking.
```
