# Practice
 大礼包	
## 问题分析：
#### 
在LeetCode商店中， 有许多在售的物品。

然而，也有一些大礼包，每个大礼包以优惠的价格捆绑销售一组物品。

现给定每个物品的价格，每个大礼包包含物品的清单，以及待购物品清单。请输出确切完成待购清单的最低花费。

每个大礼包的由一个数组中的一组数据描述，最后一个数字代表大礼包的价格，其他数字分别表示内含的其他种类物品的数量。

任意大礼包可无限次购买。
## 编程实现：
```C++
class Solution {  
public:  
    int shoppingOffers(vector<int>& price, vector<vector<int>>& special, vector<int>& needs)  
{  
    int n = price.size();  
    for (int i = n; i < 6; i++)  
    {  
        price.push_back(0);  
        needs.push_back(0);  
    }  
    for (int i=special.size()-1;i>=0;i--)  
    {  
        int t=special[i][n];  
        special[i][n]=0;  
        for (int j=n+1;j<7;j++)  
            special[i].push_back(0);  
        special[i][6]=t;  
    }  
    int d[7][7][7][7][7][7],m=special.size();  
    for (int j=0;j<=needs[0]; j++)  
    {  
        for (int k=0;k<=needs[1];k++)
        for (int p=0;p<=needs[2];p++)  
        for (int q=0;q<=needs[3];q++)  
        for (int r=0;r<=needs[4];r++)  
        for (int s=0;s<=needs[5];s++)  
            d[j][k][p][q][r][s]=j*price[0]+k*price[1]+p*price[2]+q*price[3]+r*price[4]+s*price[5];  
    }  
    for (int i=0;i<m;i++)   
    {  
        for (int j=special[i][0];j<=needs[0];j++)  
        for (int k=special[i][1];k<=needs[1];k++)  
        for (int p=special[i][2];p<=needs[2];p++)  
        for (int q=special[i][3];q<=needs[3];q++)  
        for (int r=special[i][4];r<=needs[4];r++)  
        for (int s=special[i][5];s<=needs[5];s++)  
        {  
            int t1=d[j-special[i][0]][k-special[i][1]][p-special[i][2]]  
                [q-special[i][3]][r-special[i][4]][s-special[i][5]];  
            if (t1!=INT_MAX)  
                d[j][k][p][q][r][s]=min(d[j][k][p][q][r][s],t1+special[i][6]);  
        }  
    }  
    return d[needs[0]][needs[1]][needs[2]][needs[3]][needs[4]][needs[5]];  
}  
}; 
```
## 总结体会：
这里由于needs的长度是一个动态量，而采用自底向上的方法需要遍历needs的每一个元素，为了确定循环变量j,k,p,q,r,s，我们将needs补为6位确定大小。由于special不一定划算，所以先将d存储为单价买入时的花费，之后再通过比大小确定最终值。