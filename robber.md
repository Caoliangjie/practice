# Practice
打家劫舍
## 问题分析：
#### 
你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。
## 编程实现：
```C++
class Solution {
public:
    int rob(vector<int>& nums) {
         if (nums.size()==0) return 0;
        if (nums.size()==1) return nums[0];
        if (nums.size()==2) return max(nums[0],nums[1]);
        int a[10000]={};
        a[0]=nums[0];
        a[1]=max(nums[0],nums[1]);
        for(int i=2;i<nums.size();++i)
            a[i]=max(a[i-2]+nums[i],a[i-1]);
        return a[nums.size()-1];
    }
};

```
## 总结体会：
首先想法是考虑特殊情况，一间房，两间房的时候。正常房子多的话隔一个数记一下，隔一个记一个，但是试了之后会超时。最后的办法是再开一个数组，在数组中每一次加的时候就把最大的数记录下来，不用再一一遍历，节省时间。
## P.S.：
题可以好好做，小偷不要当。