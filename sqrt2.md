# Practice
有效的完全平方数
## 问题分析：
#### 
给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。

注意：不要使用任何内置的库函数，如  sqrt。
## 编程实现：
```C++
class Solution {
public:
    bool isPerfectSquare(int x) {
         long  a=x;  
          while (a*a> x)  
        a= (a+ x/a) / 2;  
         return (a*a==x);
    }
};
```
## 总结体会：
在牛顿迭代法基础上，返回a*a==x即可，为真则是true，假则为false。
