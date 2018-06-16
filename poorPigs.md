# Practice
Poor Pigs
## 问题分析：
#### 
There are 1000 buckets, one and only one of them contains poison, the rest are filled with water. They all look the same. If a pig drinks that poison it will die within 15 minutes. What is the minimum amount of pigs you need to figure out which bucket contains the poison within one hour.
Answer this question, and write an algorithm for the follow-up general case.
## 编程实现：
```C++
class Solution {
public:
    int poorPigs(int buckets, int minutesToDie, int minutesToTest) {
        if(buckets==1) return 0;
        int ans=minutesToTest/minutesToDie+1;
        int r=1;
        for(int i=1;;i++)
        {
            r*=ans;
            if(r>=buckets)
            return i;
        }
        return 0;
    }
};
```
## 总结体会：
对于每头猪，它应有5种状态：15min、30min、45min、60min死亡和活着。假设每个桶都有对应标签（0，1，2，3，4）对应5个状态。假设有5桶水，那么只需一头猪就可以了，就可以判断那桶水有毒。在t=0时刻，第一个猪喝第一位为0的桶水，第2个猪喝下第2位为0的水，在t=15时刻，第一个猪喝第一位为1的桶水，第2个猪喝下第2位为1的水，依此类推，我们可以通过猪的死亡判断有毒的水。对于n桶水，已知基的情况下，b^x>=n即可，我们要找到x。
## P.S.
小猪真可怜，要帮忙试毒~~~~