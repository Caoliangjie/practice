# practice
平方数之和
## 问题分析：
#### 
给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a2 + b2 = c。
## 编程实现：
```C++
class Solution {
public:
    bool judgeSquareSum(int c) {
        int a=0;
        int b=sqrt(c);
        while (a<=b)
        {if (a*a+b*b==c)
        return true;
        else if (a*a+b*b>c)
            b--;
        else
        a++;}
        return 0;
    }
};
```
## 总结体会：
这里运用了三角形勾股定理的思想，避免了二重循环的时间复杂度，选择一个a比b小，这样用两边分别进行缩减，减少了一半的时间，有一点点分治的思想在里面，对于以后复杂问题的思考也有帮助。
