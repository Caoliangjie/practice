# Practice
旋转数组
## 问题分析：
#### 
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。
## 编程实现：
```C++
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int l;
        for (int i=1;i<=k;i++){
	    int n=nums.size();
            l=nums[n-1];
            nums.insert(nums.begin(),l);
            nums.erase(nums.end()-1);
    }
    }
};
```
## 总结体会：
这里强化了vector的应用....既然只要交换数组的位置，那么我们将对应的元素插入到数组前，并且将插入的那一个用erase删除，保证了全长度不变。还有一个想法是将对应元素整体放到数组后面，再重塑数组长度也是可以的。