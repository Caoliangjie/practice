# Practice
最大连续1的个数
## 问题分析：
#### 
给定一个二进制数组， 计算其中最大连续1的个数。
## 注意：
输入的数组只包含 0 和1。
输入数组的长度是正整数，且不超过 10,000。
## 编程实现：
```C++
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
    int i=0;
    int max=0;
    int s=0;
    for (i=0;i<nums.size(); i++)
    {
        if (nums[i] == 1)
        {
            s++;
            if (s > max)
            {
                max=s;
            }
        }
        else
        {
            s= 0;
        }
    }
    return max;
}
};
```
## 总结体会：
这里我们找一个二进制数组中最大的连续1的个数，我们直接遍历就可以了，把最大的寄存住，最后返回最大的max即为所找。