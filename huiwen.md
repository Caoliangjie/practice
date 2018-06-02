# Practice
回文数
## 问题分析：
#### 

判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
## 编程实现：
```C++
class Solution {
public:
bool isPalindrome(int x){
    if(x<0||x!=0&&x%10==0) return false;  
        int sum=0;   
        while(x>sum){
            sum=sum*10+x%10;
            x/=10;
        }
        return x==sum||x==sum/10;    
}
};
```
## 总结体会：
这里我们考虑到如果是负数或者这个数个位为0，就返回false。否则用一个数字记录它逆转的一半，与其另一半比较，查看是否相等。当然也要考虑数字位数的奇偶性。