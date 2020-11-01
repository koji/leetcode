## 1481. Least Number of Unique Integers after K Removals


Given an array of integers arr and an integer k. Find the least number of unique integers after removing exactly k elements.

 

Example 1:

Input: arr = [5,5,4], k = 1
Output: 1
Explanation: Remove the single 4, only 5 is left.
Example 2:
Input: arr = [4,3,1,1,3,3,2], k = 3
Output: 2
Explanation: Remove 4, 2 and either one of the two 1s or three 3s. 1 and 3 will be left.
 

Constraints:

1 <= arr.length <= 10^5
1 <= arr[i] <= 10^9
0 <= k <= arr.length

```python
def findLeastNumOfUniqueInts(self, arr: List[int], k: int) -> int:
        dic = Counter(arr)
        sorted_dic = sorted(dic.items(), key=lambda x:x[1])
        c = 0
        for v in sorted_dic:
            k=k-v[1]
            c+=1
            if k ==0:
                return len(dic)-c
            if k <0:
                return len(dic)-c+1
```


```
Runtime: 444 ms, faster than 80.76% of Python3 online submissions for Least Number of Unique Integers after K Removals.
Memory Usage: 33.6 MB, less than 5.73% of Python3 online submissions for Least Number of Unique Integers after K Removals.
```
