# practice
字符串中的第一个唯一字符
## 问题分析：
#### 
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。
## 编程实现：

```C++
class Solution {
public:
int firstUniqChar(string s) {
    vector<int> a(100,0);
    for(char c:s){
        a[c-' ']++;
    }
    for(int i=0;i<s.size();++i){
        if(a[s[i]-' ']==1)
            return i;
    }
    return -1;
}
};
```
## 总结体会：
建立一个数组，字符串每一个元素都遍历一次，并且置1,如果一个字符出现两次乃至三次，就说明遍历了不止一遍，那么就跳过了判断条件，只有第一个等于1的所在的位置被记录下来返回，若没有的话就返回了-1。
