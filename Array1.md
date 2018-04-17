# Practice
数组拆分 I
## 问题分析：
#### 
给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。

提示:

n 是正整数,范围在 [1, 10000].
数组中的元素范围在 [-10000, 10000].
## 编程实现：
```C++
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
        int ans=0,j=0;
        sort(nums.begin(),nums.end());
        for (j=0;j<nums.size();j+=2) 
        { ans+=nums[j]; }
        return ans;   
    }
};
```
## 总结体会：
基本想法是现将数组排序，然后奇数位的数字一定是最小的数了，然后按照题目要求，当然这里用了一个库函数，如果写一个快排也是可以的，库函数记得要在调用时把头文件#include <algorithm>敲上，不然会显示错误。