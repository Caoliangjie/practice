# practice
各位相加
## 问题分析：
#### 
给一个非负整数 num，反复添加所有的数字，直到结果只有一个数字。

例如:

设定 num = 38，过程就像： 3 + 8 = 11, 1 + 1 = 2。 由于 2 只有1个数字，所以返回它。
## 编程实现：
```C++
class Solution {
public:
    int addDigits(int num) {
      int   a=num;
        while(true)
        {if (a<10)
        return a;
        num=a;
        a=0;
         while(num)
         {
            a+=num%10;
            num=num/10;
         }
        }
    }
};
```
## 总结体会：
首先判断是不是一个个位数，如果有十位及以上才进行计算，每一位除10后在重新开始加数，直到最后加到一位数。
