## 200. Number of Islands

Given an m x n 2d grid map of '1's (land) and '0's (water), return the number of islands.

An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

 

Example 1:

Input: grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]
Output: 1
Example 2:

Input: grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]
Output: 3
 

Constraints:

m == grid.length
n == grid[i].length
1 <= m, n <= 300
grid[i][j] is '0' or '1'.


```python
def numIslands(self, grid: List[List[str]]) -> int:
        r = len(grid)
        c = len(grid[0])
        
        count = 0
        
        def dfs(grid, i, j):


            if i <0 or j <0 or i>=r or j>=c or grid[i][j] != '1':
                return

            grid[i][j] = '#'

            dfs(grid, i+1, j)
            dfs(grid, i-1, j)
            dfs(grid, i, j+1)
            dfs(grid, i, j-1)
        
        for i in range(r):
            for j in range(c):
                if grid[i][j] == '1':
                    dfs(grid, i, j)
                    count +=1
        return count
```



```
Runtime: 132 ms, faster than 86.94% of Python3 online submissions for Number of Islands.
Memory Usage: 15.5 MB, less than 38.11% of Python3 online submissions for Number of Islands.
```
