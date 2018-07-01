# Practice
移动零
## 问题分析：
#### 
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。
##  说明
说明:
    必须在原数组上操作，不能拷贝额外的数组。
    尽量减少操作次数。

## 编程实现：
```C++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
     for (int a=0,b=0;b<nums.size();b++) {
            if (nums[b] != 0)
                swap(nums[a++], nums[b]);
        }

    }
};
```
## 总结体会：
尽量减少交换次数，那么把不是0的数往前赶，0往后放，就可以解决。遍历一次就能完成工作。