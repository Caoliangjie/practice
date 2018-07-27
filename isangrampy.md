# Practice
有效的字母异位词
## 问题分析：
#### 
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。
### 说明
你可以假设字符串只包含小写字母。
## 编程实现：
```C++
class Solution:
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        dic1=collections.Counter(s)##记下字典的值大小
        dic2=collections.Counter(t)
        if len(dic1)!=len(dic2):##长度不同直接pass
            return False
        for key,value in dic2.items():#items可以把字典中的键值对应转化成一个列表
            if key in dic1 and value==dic1[key]:##两个对应的映射相等的的话，继续找，直到有不一样的再返回false。
                continue
            else:
                return False
        return True
```
## 总结体会：
详情注释里写的也差不多，还是说字典这个东西在python里是真的好用，对应映射值匹配那么直接表示一个对应的元素出现次数是唯一的。