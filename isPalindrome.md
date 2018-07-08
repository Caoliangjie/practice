# Practice
验证回文字符串
## 问题分析：
#### 
给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。
## 说明：
本题中，我们将空字符串定义为有效的回文串。
## 编程实现：
```C++
class Solution {
public:
    bool isPalindrome(string s) {
    vector<char> c;
    if (s=="")
        return true;
    else
    {
        for(int i=0;i<s.length();++i)
        if (((s[i]>='a')&&(s[i]<='z'))||((s[i]>='A')&&(s[i]<='Z'))||((s[i]>='0')&&(s[i]<='9')))
           c.push_back(s[i]);
        for (int j=0;j<c.size();++j)
                c[j]=tolower(c[j]);
        for(int j=0;j<c.size();++j)
        {if(c[j]!=c[c.size()-j-1])
            return false;
        }
    }
        return true;
    }
};
```
## 总结体会：
就是最纯粹的做法，把字符串中大写的转化为小写，因为是回文字符串，我们只比对到一半就可以，如果又不相等的，返回false，没有就true。然后为空时是true的可能性单独列出。