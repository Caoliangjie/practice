# Practice
旋转字符串
## 问题分析：
#### 
给定两个字符串, A 和 B。
A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。
## 编程实现：
```C++
class Solution {
public:
    bool rotateString(string A, string B) {
        return (A.length()==B.length())&&((A + A).find(B)!=string::npos);
    }
}; 
```
## 总结体会：
一开始想到直接按位进行判断，但是这样非常的麻烦。因为在字符串很长时，很难找到二者开始相同的起始点。因需要利用别的方法来做。 首先，对两个字符串的长度进行比较，如果长度一样，才会继续进行判断。 这里用到了c++中查找一个字符串是否有另一个字符串为子串的一种方法： 此处需要用到string库中的find函数与npos参数。 
首先，对于string::npos参数，这是一个常数，用来表示不存在的位置。 对于find函数，find函数的返回值是整数，只要字符串存在包含关系，其返回值必定不等于npos，但如果字符串不存在包含关系，那么返回值就一定是npos。 