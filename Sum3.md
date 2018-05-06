# Practice
最接近的三数之和
## 问题分析：
#### 
给定一个包括 n 个整数的数组 nums 和 一个目标值 target。找出 nums 中的三个整数，使得它们的和与 target 最接近。返回这三个数的和。假定每组输入只存在唯一答案。
## 编程实现：
```C++
class Solution {
public:
    int threeSumClosest(vector<int>& nums, int target) {
         sort(nums.begin(),nums.end());
        int k=0;
        int l=100000;
        for(int i=0; i<nums.size()-2; i++)
        {
            int left=i+1;
            int right=nums.size()- 1;
            while(left<right)
            {
                int a=nums[i]+nums[left]+nums[right];
                int b =abs(a-target);
                if(b<l)
                {
                    k=a;
                    l=b;
                }
                
                if(a<target)
                    left++;
                else if(a> target)
                    right--;
                else 
                    return a;
            }
        }     
        return k;
}
    };
```
## 总结体会：
今天尝试了一下中等难度的题目，这个题没有实际上也不算太难。首先给数组排序（害怕无序不好遍历），然后确定target的数，根据每三个数和来进行和target比对，接着依次改变相加的数，最后返回最接近的一个数（a或者k）。