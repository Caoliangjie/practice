# Practice
三个数的最大乘积
## 问题分析：
#### 
给定一个整型数组，在数组中找出由三个数组成的最大乘积，并输出这个乘积。
## 编程实现：
```C++
class Solution {
public:
    int maximumProduct(vector<int>& nums) {

        sort(nums.begin(),nums.end());
        int a=nums.size();
        if(nums[a-1]<0)
            return nums[a-1]*nums[a-2]*nums[a-3];
        int a = nums[a-1]*nums[a-2]*nums[a-3];
        int b = nums[a-1]*nums[0]*nums[1];
        return a>b?a:b;

    }
};

```
## 总结体会：
求三个数的最大乘积，为正还是为负要先想好。先进行排序，得到最大值。最大值为负数那么所有数都是负数。如果最大值为正值，则数组中可能存在负值，若都为正值，最大乘积为最后三位的乘积，若存在负值，可能最大值为最大数与前两位的乘积。