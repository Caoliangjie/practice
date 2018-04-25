# Practice
字符串相加
## 问题分析：
#### 
给定两个字符串形式的非负整数 num1 和num2 ，计算它们的和。

注意：

num1 和num2 的长度都小于 5100.
num1 和num2 都只包含数字 0-9.
num1 和num2 都不包含任何前导零。
你不能使用任何內建 BigInteger 库， 也不能直接将输入的字符串转换为整数形式。
## 编程实现：

```C++
class Solution {
public:
    string addStrings(string num1, string num2) {
        string s="";
        int m=num1.size(),n=num2.size(),i=m-1,j=n-1,k=0;
        while ((i >= 0) || (j >= 0))
        {
            int a = i >= 0 ? num1[i--] - '0' : 0;
            int b = j >= 0 ? num2[j--] - '0' : 0;
            int ans = a + b + k;
            s.insert(s.begin(), ans % 10 + '0');
            k = ans / 10;
        }
        return k ? "1" + s : s;
    }
};
```
## 总结体会：
高精度算法，因为题目规定不可以用Biginteger，而且不可以强制转换，这条路必然不可以走，这里采用了条件运算符进行判断，如果说有进位那么就进位，没有进位就正常计算，将最后结果存在s字符串中。
