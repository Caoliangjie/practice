# Practice
反转字符串 II
## 问题分析：
#### 
给定一个字符串和一个整数 k，你需要对从字符串开头算起的每个 2k 个字符的前k个字符进行反转。如果剩余少于 k 个字符，则将剩余的所有全部反转。如果有小于 2k 但大于或等于 k 个字符，则反转前 k 个字符，并将剩余的字符保持原样。
## 编程实现：
```C++
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
        if len(s) <= k:
            return s[::-1]
        elif (k < len(s)) and (len(s) < 2*k):
            return s[0:k][::-1] + s[k:]
        else:
            return s[0:k][::-1] + s[k:2*k] + self.reverseStr(s[2*k:], k)
```
## 总结体会：
比较暴力的做法，直接翻转字符串中每2k段的前k个字符，这样无论最后剩下什么，都能保证是2k字符中的前k个字符已经交换完毕。