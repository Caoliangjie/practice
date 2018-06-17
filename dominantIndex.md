# Practice
至少是其他数字两倍的最大数
## 问题分析：
#### 
在一个给定的数组nums中，总是存在一个最大元素 。
查找数组中的最大元素是否至少是数组中每个其他数字的两倍。
如果是，则返回最大元素的索引，否则返回-1。
## 提示
nums 的长度范围在[1, 50]。
每个 nums[i] 的整数范围在 [0, 99]。
## 编程实现：
```C++
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        int ans=0;
        int max=0;
        int second=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]>ans)
            {
                second=ans;
                ans=nums[i];
                max=i;
            }
            else if(nums[i]>second)
            {
                second=nums[i];
            }
        }        
        return (ans/2>=second)?max:-1;
    }
};
```
## 总结体会：
题目意思是找到整个数组中最大的数字和第二大的数字，看最大的是否是第二大的两倍及以上，如果是则返回索引，不是就返回-1； 对于找到这两个数字，其实可以直接用两次for循环来进行暴力查找，时间复杂度为O(n)，可以达到题目要求。不过可以进行整合，如果num[i]比最大值大，就更新最大值和第二大的值，并记录最大值的标号。否则，如果num[i]比第二大的值大，则直接更新第二大的值即可。