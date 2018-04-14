# practice
计数质数
## 问题分析：
#### 
计算所有小于非负数整数 n 的质数数量。
## 编程实现：
```C++
class Solution {
public:
    int countPrimes(int n) {
        int ans=1,i,k;
        if(n<=2)
            return 0;
        else 
        for (i=3;i<n;i+=2)
        { for(k=3;k<i;k+=2)
         { if (i%k==0)
           break;
           if(k*k>i)
           break;}
        if (k*k>i) 
        ans=ans+1;}
 return ans;}
};
```
## 总结体会：
这里用了一个比较快的方法，排除了除二外所有的偶数，只算奇数，如果判断k*k大于该数（k的平方箱相当于只算到n的平方根之前），这里先将ans置1，就是将2先算入到质数个数中。其实质数虽然是一个简单的题，真正需要理解的就是这里循环结构的运用。
