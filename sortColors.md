# Practice
 分类颜色	
## 问题分析：
#### 
给定一个包含红色、白色和蓝色，一共 n 个元素的数组，原地对它们进行排序，使得相同颜色的元素相邻，并按照红色、白色、蓝色顺序排列。
此题中，我们使用整数 0、 1 和 2 分别表示红色、白色和蓝色。
## 注意:
不能使用代码库中的排序函数来解决这道题
## 编程实现：
```C++
class Solution {  
public:  
    void sortColors(vector<int>& nums) {  
        int i=-1,j =-1,k =-1;
        int m;  
        for(m = 0; m < nums.size();m++){  
            if(nums[m] == 0){  
                nums[++k] = 2;  
                nums[++j] = 1;  
                nums[++i] = 0;  
            }  
            else if(nums[m] == 1){  
                nums[++k] = 2;  
                nums[++j] = 1;  
            }  
            else {  
                nums[++k] = 2;  
            }  
        }  
    }  
};  
```
## 总结体会：
这里设置三个变量，分别来代表红白蓝三个数组的排序，这样我们进行遍历，对比对应的颜色的的代码即可解决问题。