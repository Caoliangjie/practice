# Practice
存在重复元素
## 问题分析：
#### 
给定一个整数数组，判断是否存在重复元素。
如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。
## 编程实现：
```C++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for (int i=1;i<nums.size();++i) {
            if (nums[i]==nums[i-1]) 
                return true;
        }
        return false;
    }
};
```
## 总结体会：
我们这里直接将数组排序，然后进行两两对比，有重复元素返回true，没有返回false。本以为会超时....结果竟然能通过....有点侥幸意味总感觉。