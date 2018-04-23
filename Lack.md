# Practice
缺失数字
## 问题分析：
#### 
给出一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
## 编程实现：
```C++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int i=0;
        sort(nums.begin(),nums.end());
        while(nums[i]==i)
        {
         i++;   
        }
        return i;
    }
};
```
## 总结体会：
这里用了先排序，将每个数字对应下标，通过一层循环判断是否与当前下标匹配即可，复杂度为O（n+nlogn）。