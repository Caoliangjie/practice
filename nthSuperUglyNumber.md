# Practice
Super Ugly Number
## 问题分析：
#### 
Write a program to find the n super ugly number.
Super ugly numbers are positive numbers whose all prime factors are in the given prime list primes of size k.
## 编程实现：
```C++
class Solution {
public:
    int nthSuperUglyNumber(int n, vector<int>& primes) {
        vector<int> a(primes.size(),0);
        vector<int> d(n);
        d[0]=1;
        int l=primes.size();
        int m;
        int c=1;
        while(c<n){
            int m1=INT_MAX;
            for(int j=0;j<l;j++){
                int t=d[a[j]]*primes[j];
                if(t<m1){
                    m1=t;
                    m=j;
                }
            }
            a[m]++;
            if(d[c-1]!=m1){
                d[c]=m1;
                c++;
            }
        }
        return d[n-1];
    }
};
```
## 总结体会：
我们设d[i]代表第i个丑叔，a[i]表示第i个质数应该和第几个质数相乘。初始化设置d[0]=0,a[i]为0。设置c=1，代表正在生成第c个super ugly number，进入循环，直至c=n退出。因为prime[m1]已经和d[m]相乘过了，所以接下来应该和后一位丑叔相乘，设置a[m]++。因为可能求出的最小值m1和d[i-1]相同，需要跳过这种情况，只有不重复时，才将d[c]设置为m1，并设置c++,继续求取下一个丑叔。