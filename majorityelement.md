# Practice
求众数
## 问题分析：
#### 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在众数。
## 编程实现：

```Python
class Solution:
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        return nums[len(nums)//2]##按照众数的定义排出来的
```
## 总结体会：
按照定义，排序后如果出现次数大于n/2的数一定会出现在中间，那么返回这个数即可。