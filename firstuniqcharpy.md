# Practice
字符串中的第一个唯一字符
## 问题分析：
#### 
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。
### 注意事项：
您可以假定该字符串只包含小写字母。
## 编程实现：
```Python
class Solution:
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        dic=collections.Counter(s)
        for i in range(len(s)):
            if dic[s[i]]==1:
                return i
        return -1
```
## 总结体会：
与之前判断只出现一次的数字类似继续用字典的做法，如果在字典中这个字符存在的数目为1，就返回所在的下标，没有就返回-1.