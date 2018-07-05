# Practice
反转字符串
## 问题分析：
#### 
请编写一个函数，其功能是将输入的字符串反转过来。
## 编程实现：
```C++
class Solution {
public:
    string reverseString(string s) {
        int i=0,j=s.length()-1;
        for(i=0;i<s.length()/2;++i)
        {
            swap(s[i],s[j-i]);
        }
        return s;
    }
};
```
## 总结体会：
翻转字符串的话，只需要从中间对半进行翻转，交换字符串中先后对应位置的两个字符即可。