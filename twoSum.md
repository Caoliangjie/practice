# Practice
两数之和
## 问题分析：
#### 
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。
你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。
## 编程实现：
```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> d;
        for(int i=0;i<nums.size();++i)
        {for(int j=i+1;j<nums.size();++j)
            if ((nums[i]+nums[j]==target) && (d.size()<2))
            {     d.push_back(i);
                 d.push_back(j);
            }
        }       
        return d;
    }
};   
```
## 总结体会：
开一个新容器，因为只有两数之和就可以判断出是不是target，首先保证d的容量不会大于二并且遍历时满足两数和为target即可。