# Practice
买卖股票的最佳时机 II
## 问题分析：
#### 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。
设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。
## 说明
你不能同时参与多笔交易（你必须在再次购买前出售掉之前的股票）。
## 编程实现：
```C++
class Solution:
    def maxProfit(self, prices):#解释说这个self是个定义一样，说明后面那个是可以被引用的参数。
        """
        :type prices: List[int]
        :rtype: int
        """
        i=0
        profit=0
        for i in range(len(prices)-1):
          if prices[i+1]>prices[i]:
              profit+=prices[i+1]-prices[i]
        return profit
```
## 总结体会：
这里用python来写，然后基本思路不变，用的for循环然后接着接上最大利润即可。