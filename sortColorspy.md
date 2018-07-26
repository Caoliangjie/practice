# Practice
分类颜色
## 问题分析：
#### 
给定一个包含红色、白色和蓝色，一共 n 个元素的数组，原地对它们进行排序，使得相同颜色的元素相邻，并按照红色、白色、蓝色顺序排列。
此题中，我们使用整数 0、 1 和 2 分别表示红色、白色和蓝色。
## 说明：
不能使用代码库中的排序函数来解决这道题。
## 编程实现：
```C++
class Solution:
    def sortColors(self, nums):
        """
        :type nums: List[int]
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        num0, num2 = 0, 0
        for i,n in enumerate(nums):
            if n == 0:
                num0 += 1
            if n == 2: 
                num2 += 1
            nums[i] = 1
        if num0:
            nums[:num0] = [0] * num0
        if num2:
            nums[-num2:] = [2] * num2
```
## 总结体会：
设定下标，把下标存入i中，n存放元素，这里和正常排序不同的是，因为只有0,1,2三个元素，那只要其中2个保证所在的位置变化后，另一个有办法找到，就可以进行最终各个位置的变化。找到最后一个0的下标和第一个2的下标，把0和2安排好，中间的1也自然放好了。