# practice
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
        while (i<j)
        {
            swap(s[i++],s[j--]);
        }
        return s;
       
    }
};
```
## 总结体会：
用swap函数将首尾元素互换，即可实现翻转，注意是length函数的用法，string中长度实际是0~length-1。
