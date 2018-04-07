# practice
Roman
## 问题分析：
#### 罗马数字转整数
给定一个罗马数字，将其转换成整数。
返回的结果要求在 1 到 3999 的范围内
## 编程实现：
```C++
class Solution {
public:
    int romanToInt(string s) 
    {
        map<char,int>q;
        a['I']=1;
        a['X']=10;
        a['C']=100;
        a['M']=1000;
        a['V']=5;
        a['L']=50;
        a['D']=500;
        int r = 0;
        res = a[s[0]];
        for(int i=1;i<s.size();i++)
        {
            if(a[s[i-1]]>=a[s[i]])
                r=a[s[i]]+r;
            else                  
                r = r + a[s[i]]-2*a[s[i-1]];    
        }
        return res; 
    }
};
```
## 总结体会：
罗马数字的符号要弄清楚，并且注意罗马数字的技术规则。
