# practice
旋转数组
## 问题分析：
#### 
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。
## 说明
    尽可能想出更多的解决方案，至少有三种不同的方法可以解决这个问题。
    要求使用空间复杂度为 O(1) 的原地算法。
## 编程实现：
```C++
class Solution:
    def rotate(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        i=0
        while (i<=k-1) and (k!=0):
            nums.insert(0,nums[len(nums)-1])
            nums.pop(len(nums)-1)
            i=i+1
```
## 总结体会：
思路其实是一样的，只不过是用python语言写出来，相当于一个是中文一个是英文。其实语法差不多。这里是用了list的相关函数，insert负责将元素插入，然后pop将对应的元素移除。还是要注意缩进规则，否则还是乱出语法错误。