# Practice
两个数组的交集 II
## 问题分析
给定两个数组，写一个方法来计算它们的交集。
例如:
给定 nums1 = [1, 2, 2, 1], nums2 = [2, 2], 返回 [2, 2].
## 注意：

     输出结果中每个元素出现的次数，应与元素在两个数组中出现的次数一致。
    我们可以不考虑输出结果的顺序。

## 编程实现：
```C++
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        sort(nums1.begin(),nums1.end());
        sort(nums2.begin(),nums2.end());
        vector<int> c; 
        int n1=0;
        int n2=0;
        while(n1<nums1.size()&&n2<nums2.size()){
            if(nums1[n1] == nums2[n2]){
                c.push_back(nums1[n1]);
                ++n1;
                ++n2;
            }else if(nums1[n1] > nums2[n2]){
                ++n2;
            }else{
                ++n1;
            }
        }   
        return c;
    }
};
```
## 总结体会：
这样看，我们直接先排好顺序，以防万一后续出现问题太多。紧接着我们直接遍历对应排好的两组数，如果相等将该数置入新容器中，这里强化vector用法push_back（）。