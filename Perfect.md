# practice
完美数
## 问题分析：
#### 对于一个 正整数，如果它和除了它自身以外的所有正因子之和相等，我们称它为“完美数”。给定一个 正整数 n， 如果他是完美数，返回 True，否则返回 False
## 编程实现：
```C++
class Solution {
public:
    bool checkPerfectNumber(int num) {
      if(num == 1) return false;  
    int n = sqrt(num);  
    int ans = 1;  
    for(int i = 2;i <= n;i++){  
        if(num % i == 0){  
            ans += i+num/i;
        }  
    }  
    return ans == num; 
    }
};
```
## 总结体会：
完美数是一个比较基础的题，在学习了循环结构后可以很快做出（找因子），但是如果从1开始慢慢叠加会让时间复杂度很高，这里用了一个类似二分的方法，因为n除以每一个小因子都会得到另一个较大的因子，不必再进行计算，让运行时间变得更快。
