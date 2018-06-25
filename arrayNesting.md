# Practice
数组嵌套
## 问题分析：
#### 
索引从0开始长度为N的数组A，包含0到N - 1的所有整数。找到并返回最大的集合S，S[i] = {A[i], A[A[i]], A[A[A[i]]], ... }且遵守以下的规则。
假设选择索引为i的元素A[i]为S的第一个元素，S的下一个元素应该是A[A[i]]，之后是A[A[A[i]]]... 以此类推，不断添加直到S出现重复的元素。
## 编程实现：
```C++
class Solution {
public:
    int arrayNesting(vector<int>& nums) {
        int n=nums.size();
        int maxsize=0;
        for(int i=0;i<n;i++)
        {
            int size=0;
            for(int k=i;nums[k]>=0;size++)
            {
                int numk=nums[k];
                nums[k]=-1;
                k=numk;
            }
            maxsize=max(maxsize,size);
        }
        return maxsize;
        
    
};
```
## 总结体会：
嵌套数组一定会是一个或几个环，不可能不成环，也不可能会有除了环以外的元素。那么只要把所有元素标记完，剩下的都会重复之前的环，就不用（每次只标记第一个，完成这行后，再复原了），最后只要返回最大不重复的一组即可。
