# Practice
加一
## 问题分析：
#### 
给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。
## 编程实现：
```C++
class Solution {
public:
    vector<int> plusOne(vector<int> &digits) {
        int n=digits.size();
        for (int i=n-1;i>= 0;--i) {
            if (digits[i]==9) 
                digits[i] = 0;
            else {
                digits[i]+=1;
                return digits;
            }
        }
        if (digits.front()==0) 
            digits.insert(digits.begin(), 1);
        return digits;
    }
};
```
## 总结体会：
本以为只改变最后一位就行，果然是没有这么简单的题。它是把整体当作了一个数然后放在一个数组里，也就是会出现9999变10000的情况。那么我们就判断最后元素是不是9呗，是的话向前遍历，前面一位是9再进位。反正后面不是9只加1中间的9也不会变化。如果第一位为零，我们在插入一个1就好了。