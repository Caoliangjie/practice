# Practice
爬楼梯
## 问题分析：
#### 
假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？
## 注意
给定 n 是一个正整数。
## 编程实现：
```Python
class Solution:
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        a=1
        b=1
        while (n):
            b=b+a
            a=b-a
            n=n-1
        return a
```
## 总结体会：
这边做法是先把初值确定好，紧接着对n进行操作，每一次因为不是上1就是2，那么我们就讨论遇到这种情况的具体步骤。