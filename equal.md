# Practice
两个数组的交集
## 问题分析：
#### 
给定两个数组，写一个函数来计算它们的交集。

例子:

 给定 num1= [1, 2, 2, 1], nums2 = [2, 2], 返回 [2].
提示:

每个在结果中的元素必定是唯一的。
我们可以不考虑输出结果的顺序。
## 编程实现：
```C++
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
           sort(nums1.begin(), nums1.end());
            sort(nums2.begin(), nums2.end());
            vector<int> c;
            int k;
            for (int i = 0, j = 0; i < nums1.size() && j < nums2.size(); )
            {
                if (nums1[i] < nums2[j])
                    i++;
                else if (nums1[i] > nums2[j])
                    j++;
                else if (nums1[i] == nums2[j])
                {
                    if (c.size() == 0 || nums1[i] != k)
                    {
                        c.push_back(nums1[i]);
                        k=nums1[i];
                    }
                    i++;
                    j++;
                }
            } 
            return c;
}
};
```
## 总结体会：
这里首先对两个数组对数组进行排序，之后遍历数组中元素，并比较对应的元素，若相等，则判断其值是否与结果中最后保存的元素是否相等，相等则用push_back讲相等的添加到新开的数组中，不相等则继续向下进行遍历。