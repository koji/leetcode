## 1233. Remove Sub-Folders from the Filesystem


```
Given a list of folders, remove all sub-folders in those folders and return in any order the folders after removing.

If a folder[i] is located within another folder[j], it is called a sub-folder of it.

The format of a path is one or more concatenated strings of the form: / followed by one or more lowercase English letters. For example, /leetcode and /leetcode/problems are valid paths while an empty string and / are not.

 

Example 1:

Input: folder = ["/a","/a/b","/c/d","/c/d/e","/c/f"]
Output: ["/a","/c/d","/c/f"]
Explanation: Folders "/a/b/" is a subfolder of "/a" and "/c/d/e" is inside of folder "/c/d" in our filesystem.
Example 2:

Input: folder = ["/a","/a/b/c","/a/b/d"]
Output: ["/a"]
Explanation: Folders "/a/b/c" and "/a/b/d/" will be removed because they are subfolders of "/a".
Example 3:

Input: folder = ["/a/b/c","/a/b/ca","/a/b/d"]
Output: ["/a/b/c","/a/b/ca","/a/b/d"]
 

Constraints:

1 <= folder.length <= 4 * 10^4
2 <= folder[i].length <= 100
folder[i] contains only lowercase letters and '/'
folder[i] always starts with character '/'
Each folder name is unique.
```

```python
class Solution:
    def removeSubfolders(self, folder: List[str]) -> List[str]:
        # sort folder
        sorted_folder = sorted(folder)
        folder_set = set()
        
        for f in sorted_folder:
            # n = len(f)
            exist = False
            for i,c in enumerate(f):
                if c == '/':
                    if f[:i] in folder_set:
                        exist = True
                        break
                   
            if not exist:
                folder_set.add(f)
            
        return folder_set
```


```
Runtime: 408 ms, faster than 28.41% of Python3 online submissions for Remove Sub-Folders from the Filesystem.
Memory Usage: 30.3 MB, less than 34.29% of Python3 online submissions for Remove Sub-Folders from the Filesystem.
```
