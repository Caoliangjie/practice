# Practice
计数质数
## 问题分析：
#### 
统计所有小于非负整数 n 的质数的数量。
## 编程实现：
```Python
class Solution:
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
         """
        if n < 3:
            return 0
        prime = [1] * n
        prime[0] = prime[1] = 0
        for i in range(2, int(n**0.5) +1):
            if prime[i] == 1:
                prime[i*i:n:i] = [0]*len(prime[i*i:n:i])
        return sum(prime)
```
## 总结体会：
这里如果直接用遍历方法是会超时的，为了解决这个超时的问题，我们采取一种清奇的思路。将 2~n 的各个数放入表中，然后在2的上面画一个圆圈，然后划去2的其他倍数；第一个既未画圈又没有被划去的数是3，将它画圈，再划去3的其他倍数；现在既未画圈又没有被划去的第一个数是5，将它画圈，并划去5的其他倍数……依次类推，一直到所有小于或等于n的各数都画了圈或划去为止。这样最后得到的就是记下的质数个数。