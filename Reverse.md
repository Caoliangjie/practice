# practice
  翻转整数
## 问题分析：
#### 
给定一个范围为 32 位 int 的整数，将其颠倒
## 编程实现：
```C++
class Solution {
public:
    int reverse(int x) {
        int a=0;
        while (x)
        {  int b=a*10+x%10;
           if (b/10!=a)
               return 0;
         a=b;
         x=x/10;   
        }
    return a;
    }
};
```
## 总结体会：
首先x取余得到个位数字存到b中，紧接着将这个数字作为最高位赋给a让其继续进程，同时x从最高位移到次高位继续翻转，如果为0，那么也一样，a*10依然是0.
