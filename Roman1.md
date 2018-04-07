# practice
Daily practice
## 问题分析：
#### 二进制数相加
补全较短二进制字符串然后对应相加
## 编程实现：
```C++
class Solution {
public:
    int romanToInt(string s) 
    {
        map<char,int>q;
        q['I']=1;
        q['X']=10;
        q['C']=100;
        q['M']=1000;
        q['V']=5;
        q['L']=50;
        q['D']=500;
        int res = 0;
        res = q[s[0]];
        for(int i=1;i<s.size();i++)
        {
            if(q[s[i-1]]>=q[s[i]])
                res=q[s[i]]+res;
            else                  
                res = res + q[s[i]]-2*q[s[i-1]];    
        }
        return res; 
    }
};
## 总结体会：
二进制数相加并且保存在string中需要考虑如何将string和int之间互相转换且每位相加时可能进位会影响相加的结果。

