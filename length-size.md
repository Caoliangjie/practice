# Practice
字符的最短距离
## 问题分析：
#### 
给定一个字符串 S 和一个字符 C。返回一个代表字符串 S 中每个字符到字符串 S 中的字符 C 的最短距离的数组。
## 编程实现：
```C++
class Solution {
public:
    vector<int> shortestToChar(string S, char C) {
        vector<int> a(S.size(),0);
        vector<int> b;
        for(int i=0;i<S.size();i++)
            if(S[i]==C)
                b.push_back(i);
        for(int i=0;i<S.size();i++){
            if(S[i]!=C){
                int n=S.size();
                for(int j = 0;j<b.size();j++)
                    n=n<abs(b[j]-i)?n:abs(b[j]-i);
                a[i]=n;
            }
        }
        return a;
    }
};
```
## 总结体会：
建立一个数组b将S中所有C存在的位置保存下来。然后遍历S字符串，将其与C中保存的位置依次求距离(即为差的绝对值)，然后保存下来最短距离就可以。