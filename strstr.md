# practice
  实现strstr
## 问题分析：
#### 
实现strstr函数，没有返回-1
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
判断两组是否一样，做法比较简单，主要是遍历后的标记好即可。
