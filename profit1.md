# Practice
买卖股票的最佳时机
## 问题分析：
#### 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。
## 编程实现：
```C++
class Solution {
public:
    int maxProfit(vector<int> &prices) {  
        int ans=0;  
        if(prices.size()<2)  
            return ans;  
        int a=prices[0];  
        for(int i=1;i<prices.size();i++)  
        {  
            int b=prices[i];  
            ans=max(ans,b-a);  
            a=min(a,b);  
        }  
        return ans;  
    }  
};        
```
## 总结体会：
通过分析之后我们发现，对于每一天来说能得到的最大利益就是它和之前最低点的差。因为每天只能完成一笔交易，而且不能买之前卖的股票，那么只要不断遍历每一天，找到相对比较最大的和最小的一天，就可以得到最大利润。