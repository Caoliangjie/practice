# Practice
排列硬币
## 问题分析：
#### 
你总共有 n 枚硬币，你需要将它们摆成一个阶梯形状，第 k 行就必须正好有 k 枚硬币。

给定一个数字 n，找出可形成完整阶梯行的总行数。

n 是一个非负整数，并且在32位有符号整型的范围内。
## 编程实现：
```Python
class Solution:
    def arrangeCoins(self, n):
        """
        :type n: int
        :rtype: int
        """
        low = 0
        high = n
        while low <= high:
            mid = int((low + high) / 2)
            if 0 <= n - (mid+1)*mid/2 < mid + 1:
                return mid
            elif n - (mid+1)*mid/2 >= mid + 1:
                low = mid + 1
            elif n - (mid+1)*mid/2 < 0:
                high = mid - 1
```
## 总结体会：
这里的做法用的是数学思路，因为第k行必须放k个，这样的话根据求和公式n=(m+1)*m/2,把未知数反代回来得到最后的m即为我们所求的行数，因为n是一个32位有符号整型，int放不开，所以用了long。