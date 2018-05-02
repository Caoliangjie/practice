# Practice
移除元素
## 问题分析：
#### 
给定一个数组 nums 和一个值 val，你需要原地移除所有数值等于 val 的元素，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。
## 编程实现：
```C++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int n=nums.size(),i=0;
        while(i<n){
            if(nums[i]==val){
                n--;
                nums[i]=nums[n];
            } else{
                i++;
            }
        }
        return n;
    }
};
```
## 总结体会：
这个题比较简单，先从当前位置i，顺着找，如果相等就把位置交换，然后n--，i++，没有则继续往下遍历，直到到数组最后返回n的长度即为最终的长度。