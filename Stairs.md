# Practice
爬楼梯
## 问题分析：
#### 
假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数。
## 编程实现：
```C++
class Solution {
public:
    int climbStairs(int n) {
      int a=1,b=1;
        while (n--)
            a=(b+=a)-a;
           return a;
    }
};
```
## 总结体会：
最基础的想法自然是用递归做法来做，但是这里递归做法会在oj时超时，那么我们换一种思路，如果用递推的方法，从末尾开始找一次是1和2的做法，初始时a=1，b置2，接着向下依次b增大，a增大，直到n--不为真停止。