# Practice
宝石与石头
## 问题分析：
#### 
给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。
## 编程实现：
```C++
class Solution {
public:
       int numJewelsInStones(string J, string S) {
        int i = 0;
        for(int j=0; j<J.length(); j++) {
            for(int s=0;s<S.length(); s++) {
                if(J[j] == S[s])
                 i++;
            }
        }
        return i;
    }
};
```
## 总结体会：
还是考察对字符串的理解，首先要遍历数组找s中的j是否存在，存在那么就记录在i中，没有就不记录。