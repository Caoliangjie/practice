# Practice
缺失数字
## 问题分析：
#### 
给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
##实例
###输入: 
"10101"
###输出: 
4
###解释: 
有4个子串：“10”，“01”，“10”，“01”，它们具有相同数量的连续1和0。
## 编程实现：
```Python
class Solution:
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        for i in range(len(nums)):
            if i!=nums[i]:
                return  i
        return len(nums)

```
## 总结体会：
做法比较粗暴，先排序后看下标和元素是否一致，因为是从0开始所以不用担心加1减1问题，没有的话就把长度返回（说明元素都够了）。