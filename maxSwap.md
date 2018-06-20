# Practice
最大交换	
## 问题分析：
#### 
给定一个非负整数，你至多可以交换一次数字中的任意两位。返回你能得到的最大值。
## 编程实现：
```C++
class Solution {
public:
    int maximumSwap(int num) {
        int res=num;
        string a=to_string(num);
        for (int i=0;i< a.length();i++)
        {
            for (int j=i+1;j<a.length();j++)
            {
                swap(a[i], a[j]);
                res=max(res, stoi(a));
                swap(a[i], a[j]);
            }
        }
        return res;
    }
};  
```
## 总结体会：
这里我们还是要进行遍历，然后直接交换进行多次比对返回最后的最大值即可。
## P.S.
以为暴力遍历会超时...结果没有...嗯...