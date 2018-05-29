# Practice
使用最小花费爬楼梯
## 问题分析：
#### 
数组的每个索引做为一个阶梯，第 i个阶梯对应着一个非负数的体力花费值 cost[i]（索引从0开始）。

每当你爬上一个阶梯你都要花费对应的体力花费值，然后你可以选择继续爬一个阶梯或者爬两个阶梯。

您需要找到达到楼层顶部的最低花费。在开始时，你可以选择从索引为 0 或 1 的元素作为初始阶梯。
## 编程实现：
```C++
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        if(cost.size()==0){
            return 0;
        }
        if(cost.size()==1){
            return cost[0];
        }
        if(cost.size()==2){
            return std::min(cost[0],cost[1]);
        }
        int a[1024];
        a[0] = 0;
        a[1] = 0;
        for(int i=2;i<=cost.size();i++){
            a[i] = min(a[i-1]+cost[i-1],a[i-2]+cost[i-2]);
        }
        return a[cost.size()];
    }
};      
```
## 总结体会：
我们用a[i]表示走到第i阶的成本，要求a[i],我们只需在"到前一个的成本+当前的成本"和"到前两阶的成本+前两个成本"取最小即可。因为a[0]和a[1]都可以作为起点，所以成本都为0。注意一下爬两阶只需要那两阶的第一个成本作为总成本不需要两段成本相加即可。