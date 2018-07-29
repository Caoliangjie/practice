# Practice
最长公共前缀
## 问题分析：
#### 
编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。
## 编程实现：
```C++
class Solution:
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if len(strs) == 0:  
            return "" ##没有返回0
        for i in range(1, len(strs)):  
            l1 = len(strs[0])  
            l2 = len(strs[i])  
            if l1 > l2:  
                length = l2  
            else:  
                length = l1  
            if length == 0:  
                return "" 
            strs[0] = strs[0][0:length]  
            for j in range(length):  
                if strs[0][j] != strs[i][j]:  
                    strs[0] = strs[0][0:j]  
                    break 
        return strs[0]
```
## 总结体会：
判断每一段的长度，把最短的公共长度存到list第一位，期间不断进行比对，一旦出现长度不一样的就跳。