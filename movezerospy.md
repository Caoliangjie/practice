# practice
移动零
## 问题分析：
#### 
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。
## 编程实现：
```Python
class Solution:
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        j = 0
        for i in range(len(nums)):
            if nums[i] != 0:
                nums[j], nums[i] = nums[i], nums[j]
                j += 1 
```
## 总结体会：
因为涉及到最后还有要记住哪个遍历过和没遍历过得问题。如果想当然的使用直pop和append会出问题（[0,0,1]会产生i的位置变化，所以不能这么做），这里是用j来记录走过的位置，避免产生分歧。
