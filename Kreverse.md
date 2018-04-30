# Practice
验证回文串
## 问题分析：
#### 
给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。

说明：本题中，我们将空字符串定义为有效的回文串。
## 编程实现：
```C++
class Solution {
public:
    bool isPalindrome(std::string s)
    {
        if(s.empty())
        {
            return true;
        }
        
        int b=s.size()-1;
        int a=0;
        
        while(a<b)
        {
            while(!::isalnum(s[a]))
            {
                ++a;
                if(a>=b)
                {
                    break;
                }
            }
            
            while(!::isalnum(s[b]))
            {
                --b;
                if(b<=a)
                {
                    break;
                }
            }
            
            if(a>=b)
            {
                break;
            }
            
            s[a] = ::tolower(s[a]);
            s[b] = ::tolower(s[b]);
            if(s[a] != s[b])
            {
                return false;
            }
            
            ++a;
            --b;
        }
        
        return true;
        
    }
};

```
## 总结体会：
非字母数字字符不参加判断,这里非字母数字字符可使用isalnum函数判断，只要是字符就可以读入，那么忽略大小写，使用tolower将两个字符皆转成小写，之后就是两边分别判断是否有一致，一致则为回文数，不一致那么就不是。
