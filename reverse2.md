# Practice
反转字符串 II
## 问题分析：
#### 
给定一个字符串和一个整数 k，你需要对从字符串开头算起的每个 2k 个字符的前k个字符进行反转。如果剩余少于 k 个字符，则将剩余的所有全部反转。如果有小于 2k 但大于或等于 k 个字符，则反转前 k 个字符，并将剩余的字符保持原样。
## 编程实现：
```C++
class Solution {
public:
    string reverseStr(string s, int k) {
        for (int i = 0; i < s.size(); i += 2 * k) {
            reverse(s.begin() + i, min(s.begin() + i + k, s.end()));
        }
        return s;
    }
};
```
## 总结体会：
比较暴力的做法，直接翻转字符串中每2k段的前k个字符，这样无论最后剩下什么，都能保证是2k字符中的前k个字符已经交换完毕。