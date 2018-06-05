# Practice
范围求和 II
## 问题分析：
#### 
给定一个初始元素全部为 0，大小为 m*n 的矩阵 M 以及在 M 上的一系列更新操作。
操作用二维数组表示，其中的每个操作用一个含有两个正整数 a 和 b 的数组表示，含义是将所有符合 0 <= i < a 以及 0 <= j < b 的元素 M[i][j] 的值都增加 1。
在执行给定的一系列操作后，你需要返回矩阵中含有最大整数的元素个数。
## 说明：
m 和 n 的范围是 [1,40000]。
a 的范围是 [1,m]，b 的范围是 [1,n]。
操作数目不超过 10000。
## 编程实现：
```C++
class Solution {
public:
    int maxCount(int m, int n, vector<vector<int>>& ops) {
        if(ops.size()==0)  
            return m*n;  
        int a= ops[0][0];  
        int b= ops[0][1];  
        for(int i=1;i<ops.size();i++)  
        {  
            a=min(ops[i][0],a);  
            b=min(ops[i][1],b);  
        }  
        return a*b;  
    }  
};  
```
## 总结体会：
这里我们观察到矩阵是mxn，如果数组大小为0，那就返回矩阵大小。我们从头开始遍历，小的和a，b进行分别对比交换，将符合的元素挑选出来后axb即为最后含有的最大元素个数。