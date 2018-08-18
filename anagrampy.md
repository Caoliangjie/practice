# practice
有效的字母异位词
## 问题分析：
#### 
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。
## 编程实现：

```C++
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        if len(t) != len(s):
            return False
        c = set(t)
        for i in c:
            if t.count(i) != s.count(i):
                return False
        return True
```
## 总结体会：
训练到字符串，但是做法感觉和字符数组差不多，把其顺序排好，然后接着比对，有不一样的那就说明是错的，然后就是之前没有通过两个都为空的情况，最后加上之后通过，嗯..
