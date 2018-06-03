# Practice
提莫攻击
## 问题分析：
#### 
在《英雄联盟》的世界中，有一个叫“提莫”的英雄，他的攻击可以让敌方英雄艾希（编者注：寒冰射手）进入中毒状态。现在，给出提莫对艾希的攻击时间序列和提莫攻击的中毒持续时间，你需要输出艾希的中毒状态总时长。
你可以认为提莫在给定的时间点进行攻击，并立即使艾希处于中毒状态。
## 编程实现：
```C++
class Solution {
public:
    int findPoisonedDuration(vector<int>& timeSeries, int duration) {
        if (timeSeries.size() <=0)
            return 0;
        int ans=0;
        for (int i=1; i<timeSeries.size(); i++)
        {
            if (timeSeries[i]-timeSeries[i-1]>=duration)
                ans+=duration;
            else
                ans+=timeSeries[i]-timeSeries[i-1];
        }
        ans+=duration;
        return ans;
    }
};
```
## 总结体会：
因为以前也是解除过这个游戏，所以见到这个题目未免有些激动（想起了以前还有一道魔兽的题，是广搜的）。这个题目看上去花里胡哨，其实也就是一个计算间隔的总和的问题，比较容易。这样我们就对存放攻击时间的序列进行遍历，判断是否中毒，将时间算在ans中。
## 闲谈：
实际上玩过游戏的知道提莫出寒冰权杖或者冰霜战锤后点人（普通攻击）配合触发e技能被动后基本可以做到每秒都中毒（想起了当时上单被提莫支配的恐惧....团战可以输，提莫必须死。）