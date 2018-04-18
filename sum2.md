# Practice
二进制求和
## 问题分析：
#### 
给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。
## 编程实现：
```C++
class Solution {
public:
    string addBinary(string a, string b) {  
        string ans = "";  
        int c = 0, n = 0;  
        int i = a.size() - 1, j = b.size() - 1;  
        for (; i >= 0 && j >= 0; i--, j--)  
        {  
            n = (a[i] - '0') + (b[j] - '0') + c;  
            c = n / 2;  
            n = n % 2;  
            ans += ('0' + n);  
        }  
        for (; i >= 0; i--)  
        {  
            n = (a[i] - '0') + c;  
            c = n / 2;  
            n = n % 2;  
            ans += ('0' + n);  
        }  
        for (; j >= 0; j--)  
        {  
            n = (b[j] - '0') + c;  
            c = n / 2;  
            n = n % 2;  
            ans += ('0' + n);  
        }  
        if (c != 0)  
        {  
            ans += ('0' + c);  
        }  
        i = 0; j = ans.size() - 1;  
        while (i < j)  
        {  
            char t = ans[i];  
            ans[i] = ans[j];  
            ans[j] = t;  
            i++; j--;  
        }  
        return ans;  
    }  
};  
  

```
## 总结体会：
a，b是两个要求和的二进制数，用字符串表示，对于字符串进行遍历，逐位进行加法，如果判断出进位，并且要判断需不需要补零，进行移位。虽然麻烦了点，但是比较直观的一个做法，当然也可以想想能不能把其转化为10进制来计算，当然这里输入应该用一个整型或者double型来进行计算。