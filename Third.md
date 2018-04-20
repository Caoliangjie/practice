# Practice
第三大的数
## 问题分析：
#### 
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数.
## 编程实现：
```C++
class Solution {
public:
    int thirdMax(vector<int>& nums) {
        int k,j,f;
        j=1;f=nums[0];
        sort(nums.begin(),nums.end(),greater<int>());
        for (int i=1; i<nums.size();++i)
        {   if ((nums[i]<nums[0])&&(j<3))
            { f=nums[0];
              nums[0]=nums[i];
                nums[i]=f;
             ++j;
            }     
        }
        if (j<3)
            return f;
        else 
            return nums[0];
            }
};
```
## 总结体会：
要求时间复杂度为O(n)，我这个时间复杂度是O(n+nlogn)，但是oj出来竟然能够通过，这里我的方法就是降序排序后一一枚举，然后找到第三大的数时输出，没有则返回最大数。这里我觉得可能是由于数据中重的数据很多，所以nlogn非常小到可以忽略不计。如果只遍历一遍的话，应该需要用nums[0]来跟所有的数比较，如果有不一样的记录下来，相当于多开辟一个空间来存数。