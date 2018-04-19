# Practice
求众数
## 问题分析：
#### 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且数组中的众数永远存在。
## 编程实现：
```C++
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int ans=1,k=0,i=0;
        k=nums[0];
        for(i=0;i<nums.size();i++)
        {     if (ans==1)
            {      ans++;
                k=nums[i];
    }
        else 
            if (k==nums[i])
        {
                ans++;
            }  
        else 
            ans--;}
        return k;
    }
};
```
## 总结体会：
本来的想法是想排序后再重新计算出现的频率，后来想想其实这个过程可以在遍历的时候解决就行，不用搞得复杂。首先这里讲头元素确定后，判断如果有相等的数时，判断条件加一，否则不相等减一，并且将这个元素更新。