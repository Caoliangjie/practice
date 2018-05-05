# Practice
1比特与2比特字符
## 问题分析：
#### 
有两种特殊字符。第一种字符可以用一比特0来表示。第二种字符可以用两比特(10 或 11)来表示。

现给一个由若干比特组成的字符串。问最后一个字符是否必定为一个一比特字符。给定的字符串总是由0结束。
## 编程实现：
```C++
class Solution {
public:
    bool isOneBitCharacter(vector<int>& bits) {
        int l=bits.size(); 
        int i=0;
        while(i<l-1) 
            {
            if(bits[i] == 0) {
                if(i+1<l) 
                   i++;
                else 
                    break;
            }
            else
            {
                if (i+2<l) 
                 i+=2;
                else 
                    break;
            }
        }
        if(i==l||(i==l-1&&bits[l-1]==0))
            return true;
        else 
            return false;
    }
};
```
## 总结体会：
按照题目要求可知，第一种字符用0，第二种用10和11，那么首先判断开始是不是0，不是0那么肯定是一个两比特数了，然后我们按照给定条件一个一个遍历，最后看是否匹配完两比特数或者是剩余一比特数。接着输出正确还是错误。