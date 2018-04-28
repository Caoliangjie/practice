# Practice
x 的平方根
## 问题分析：
#### 
实现 int sqrt(int x) 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。
## 编程实现：
```C++
class Solution {
public:
    int mySqrt(int x) {
   long  a=x;  
    while (a*a> x)  
        a= (a+ x/a) / 2;  
    return a;  
    }
};
```
## 总结体会：
牛顿法开平方，很基础的一个做法，牛顿法的意思是用xn+1=(xn+a/xn)/2的迭代公式，无限逼近这个根，这里用long长整型是为了怕超出数据范围。
