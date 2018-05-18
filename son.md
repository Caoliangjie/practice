# Practice
实现strStr()
## 问题分析：
#### 
实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
## 编程实现：
```C++
class Solution {
public:
    int strStr(string haystack, string needle) {
        int m = haystack.size();
        int n = needle.size();
        for(int i = 0; i <= m-n; i ++)
        {
            int j;
            for(j = 0; j < n; j ++)
            {
                if(haystack[i+j] != needle[j])
                    break;
            }
            if(j == n)
                return i;
        }
        return -1;
    }
};
```
## 总结体会：
比较简洁的做法，从开始就开始遍历，有匹配到needle的就跳出，有就返回位置，没有那就返回-1。整体是要理解字符串的函数Strstr的意义就很明了。