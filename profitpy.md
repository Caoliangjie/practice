# Practice
买卖股票的最佳时机
## 问题分析：
#### 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。
如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。
注意你不能在买入股票前卖出股票。
## 示例:
输入: [7,1,5,3,6,4]
输出: 5
解释: 在第 2 天（股票价格 = 1）的时候买入，在第 5 天（股票价格 = 6）的时候卖出，最大利润 = 6-1 = 5 。
### 注意
利润不能是 7-1 = 6, 因为卖出价格需要大于买入价格。
## 编程实现：
```C++
class Solution:
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        ans=0  
        if len(prices)<2:  
            return ans  
        a=prices[0]  
        for i in range(1,len(prices)):
            b=prices[i] 
            ans=max(ans,b-a)  
            a=min(a,b)  
        return ans  
```
## 总结体会：
基本思路还是贪心，对于Python的话用list进行修改，只要能产生利润就可以把股票卖掉，不需要考虑之后的，毕竟股票这种东西能赚就是不赔。