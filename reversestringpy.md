# Practice
反转字符串
## 问题分析：
#### 
请编写一个函数，其功能是将输入的字符串反转过来。
## 编程实现：
```C++
class Solution:
    def reverseString(self, s):
        """
        :type s: str
        :rtype: str
        """
        s1=""
        for i in range(len(s)):
            s1+=s[-1-i]
        return s1
```
## 总结体会：
python的字符串操作，确实是比较基础暴力的解法。直接利用python字符串的特性让另一个新字符串反向读入该字符串就可以完成这个操作。