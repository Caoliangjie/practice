# Practice
只出现一次的数字 II
## 问题分析：
#### 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现了三次。找出那个只出现了一次的元素。
## 编程实现：
```C++
class Solution {
public:
int singleNumber(vector<int>& nums) {
    sort(nums.begin(), nums.end());
    for (int i = 1; i < nums.size() - 1; ++i) {
        if ((nums[i] != nums[i - 1]) && (nums[i] != nums[i + 1]))
            return nums[i];
    }               
    if (nums[0] != nums[1]) return nums[0];
    else if (nums[nums.size() - 1] != nums[nums.size() - 2])
        return nums[nums.size() - 1];
}
};
  
```
## 总结体会：
这里直接进行排序后，从排好序的数字进行遍历，按照题目要求找到那个只出现一次的就是我们要求的元素。本以为会超时，然而并没有....恩。