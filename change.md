# Practice
找不同
## 问题分析：
#### 
给定两个字符串 s 和 t，它们只包含小写字母。

字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。

请找出在 t 中被添加的字母。
## 编程实现：
```C++
class Solution {
public:
    char findTheDifference(string s, string t) {
        sort(s.begin(),s.end());
        sort(t.begin(),t.end());
        int i=0;
        while(s[i]==t[i]){
            i++;
        }
        return t[i];
    }
};

```
## 总结体会：
做法先排序，将字母按照大小排列，这样的话找到第一个不一样的字母那么就是改变的字母，很简单。
