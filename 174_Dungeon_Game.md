## 174. Dungeon Game

The demons had captured the princess (P) and imprisoned her in the bottom-right corner of a dungeon. The dungeon consists of M x N rooms laid out in a 2D grid. Our valiant knight (K) was initially positioned in the top-left room and must fight his way through the dungeon to rescue the princess.

The knight has an initial health point represented by a positive integer. If at any point his health point drops to 0 or below, he dies immediately.

Some of the rooms are guarded by demons, so the knight loses health (negative integers) upon entering these rooms; other rooms are either empty (0's) or contain magic orbs that increase the knight's health (positive integers).

In order to reach the princess as quickly as possible, the knight decides to move only rightward or downward in each step.

 

Write a function to determine the knight's minimum initial health so that he is able to rescue the princess.

For example, given the dungeon below, the initial health of the knight must be at least 7 if he follows the optimal path RIGHT-> RIGHT -> DOWN -> DOWN.


https://leetcode.com/problems/dungeon-game/


```python
def calculateMinimumHP(self, dungeon: List[List[int]]) -> int:
        
        m = len(dungeon)
        n = len(dungeon[0])
        
        dungeon[-1][-1] = max(1, 1-dungeon[-1][-1])
        
        for c in range(n-2, -1, -1):
            dungeon[m-1][c] = max(1, dungeon[m-1][c+1] - dungeon[m-1][c])
        
        for r in range(m-2, -1, -1):
            dungeon[r][n-1] = max(1, dungeon[r+1][n-1] - dungeon[r][n-1])
            
        
        for r in range(m-2, -1, -1):
            for c in range(n-2, -1, -1):
                dungeon[r][c] = max(1, min(dungeon[r+1][c]-dungeon[r][c], dungeon[r][c+1]-dungeon[r][c]))
                  
        return dungeon[0][0]
```


```
Runtime: 68 ms, faster than 92.22% of Python3 online submissions for Dungeon Game.
Memory Usage: 15.2 MB, less than 68.46% of Python3 online submissions for Dungeon Game.
```
