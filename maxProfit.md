# Practice
买卖股票的最佳时机 II
## 问题分析：
#### 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。
设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。
## 编程实现：
```C++
class Solution {
public:
    int maxProfit(vector<int> &prices) {
        if(prices.size()<=0) {
            return 0;
        }
        int profit=0;
        for(int i=1;i<prices.size(); i++) {
            if(prices[i]-prices[i-1]>0) {
                profit+=(prices[i]-prices[i-1]);
            }
        }
        return profit;
    }
};
```
## 总结体会：
贪心算法，只要是能第二天比第一天能赚钱我们就卖，实际上这个题确实是简单....想了想因为天数是不可逆的...没法进行先排序只能一天一天开始算...嗯