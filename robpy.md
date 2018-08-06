# Practice
打家劫舍
## 问题分析：
#### 
你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。
## 编程实现：
```C++
class Solution:
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        a=[]
        i=2
        if len(nums)==0:
            return 0
        if len(nums)==1: 
            return nums[0]
        if len(nums)==2:
            return max(nums[0],nums[1])
        a.append(nums[0])
        a.append(max(nums[0],nums[1]))
        for i in range(2,len(nums)):
            a.append(max(a[i-2]+nums[i],a[i-1]))
        return a[len(nums)-1]
```
## 总结体会：
用最基础的列表的做法(这几天正好在加强基础语法的练习),直接就按照隔着房子最多的和最大的选择,比较简单粗暴.