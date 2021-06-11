## 1507. Reformat Date

```
Given a date string in the form Day Month Year, where:

Day is in the set {"1st", "2nd", "3rd", "4th", ..., "30th", "31st"}.
Month is in the set {"Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"}.
Year is in the range [1900, 2100].
Convert the date string to the format YYYY-MM-DD, where:

YYYY denotes the 4 digit year.
MM denotes the 2 digit month.
DD denotes the 2 digit day.
 

Example 1:

Input: date = "20th Oct 2052"
Output: "2052-10-20"
Example 2:

Input: date = "6th Jun 1933"
Output: "1933-06-06"
Example 3:

Input: date = "26th May 1960"
Output: "1960-05-26"
 

Constraints:

The given dates are guaranteed to be valid, so no error handling is necessary.
```


```python
class Solution:
    def reformatDate(self, date: str) -> str:
        m_dic = {"Jan":'01', "Feb":'02', "Mar":'03', "Apr":'04', "May":'05', "Jun":'06', "Jul":'07', "Aug":'08', "Sep":'09', "Oct":'10', "Nov":'11', "Dec":'12'}
        
        date_str = date.split()
        y = str(date_str[2])
        m = str(m_dic[date_str[1]])
        d = str(date_str[0][:-2])
        if len(d) == 1:
            d = '0' + d
        # print(y + '-' + m + '-' + d)
        return '{}-{}-{}'.format(y, m, d)
```



```
Runtime: 52 ms, faster than 6.19% of Python3 online submissions for Reformat Date.
Memory Usage: 14.4 MB, less than 19.79% of Python3 online submissions for Reformat Date.
```
