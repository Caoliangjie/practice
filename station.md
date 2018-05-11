# Practice
交替位二进制数
## 问题分析：
#### 
给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。
### 示例 1:
#### 输入: 
5
#### 输出: 
True
#### 解释:
5的二进制数是: 101

## 编程实现：
```C++
class Solution {
public:
    bool hasAlternatingBits(int n) {
        int a=-1;
        while (n>0) {
            if (n&1==1) {
                if (a==1) 
                    return false;
                    a=1;
            } 
            else 
            {
                if (a==0) 
                    return false;
                a=0;
            }
            n>>=1;
        }
        return true;
    }
};
```
## 总结体会：
我们按位检测。a来记录上一个位置的值初始化为-1然后我们用‘与’1的方法来获取最低位的值，如果是1那么当此时a已经是1的话说明两个1相邻了，返回false，否则a赋值为1。同理如果是0，那么当此时a已经是0的话，说明两个0相邻了，返回false，否则a赋值为0。判断完别忘了将n向右移动一位。如果while循环退出了，返回true。
