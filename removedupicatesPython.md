# practice
从排序数组中删除重复项
## 问题分析：
#### 
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。
## 编程实现：
```Python3
class Solution:
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        i=0
        while i<len(nums)-1:
            if (nums[i]==nums[i+1]):
                nums.remove(nums[i])
            else:
                i=i+1
        return len(nums)
```
## 总结体会：
尝试一下用python3来写一下代码，思想和c++那里差不多。这里用了列表的命令进行完成。在列表规定范围之内进行遍历，如果有相同的两个数（前后对比），那么把后面的数删除即可。最后返回nums列表的长度即可。
