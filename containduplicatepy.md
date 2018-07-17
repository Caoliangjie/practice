# Practice
存在重复
## 问题分析：
#### 
给定一个整数数组，判断是否存在重复元素。
如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。
## 编程实现：
```C++
class Solution:
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        dic=collections.Counter(nums)##用了字典的做法。
        for value in dic.values():
            if value>=2:
                return True
        return False

```
## 总结体会：
这里用到了字典的概念，直接统计字典中元素出现的频率，大于二的就返回正确，没有的就返回false。这是python一个独有的应用。