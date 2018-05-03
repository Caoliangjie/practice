# Practice
 反转字符串中的元音字母
## 问题分析：
#### 
编写一个函数，以字符串作为输入，反转该字符串中的元音字母。

示例 1：
给定 s = "hello", 返回 "holle".

示例 2：
给定 s = "leetcode", 返回 "leotcede".

## 注意:
元音字母不包括 "y".
## 编程实现：
```C++
class Solution {
public:
    string reverseVowels(string s) {
        int a= 0,n=s.size()-1;
        while (a<n) {
            a=s.find_first_of("aeiouAEIOU",a);
            n=s.find_last_of("aeiouAEIOU",n);
            if (a<n) {
                swap(s[a++], s[n--]);
            }
        }
        return s;
    }
};
```
## 总结体会：
这里用了字符串函数find_first_of()和 find_last_of()来进行查找，从头和尾分别查找有没有元音字母，有的话，用swap交换位置，然后继续向下进行查找，最后返回到已经交换位置的原来字符串s。
