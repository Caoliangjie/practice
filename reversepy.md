# Practice
颠倒整数
## 问题分析：
#### 
给定一个 32 位有符号整数，将整数中的数字进行反转。
## 编程实现：
```C++
class Solution
{
class Solution:
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        if x >= 0:
            x = int(str(x)[::-1]) 
        else:
            x=-int(str(-x)[::-1])
        if x < 2147483648 and x >= -2147483648:
            return x
        else:
            return 0
```
## 总结体会：
在python里搞循环的话会非常麻烦（容易超时），直接先把数字直接反向输出转为字符串再转为数字，最后判断是不是超出范围，没超出才返回颠倒的整数.