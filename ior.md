# Practice
整数转罗马数字
## 问题分析：
#### 
罗马数字包含以下七种字符： I， V， X， L，C，D 和 M。
例如， 罗马数字 2 写做 II ，即为两个并列的 1。12 写做 XII ，即为 X + II 。 27 写做  XXVII, 即为 XX + V + II 。
通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况:
I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。
X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 
C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。
给定一个整数，将其转为罗马数字。输入确保在 1 到 3999 的范围内。
## 编程实现：
```C++
class Solution {
public:
        string intToRoman(int num) {   
        if(num <= 0) 
            return "";  
        string s1 = "";  
        static int a[13] = {1000, 900, 500, 400, 100,90, 50, 40, 10, 9, 5, 4, 1};  
        static string b[13] = {"M","CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};  
          
        for(int i = 0;i<13&&num>0; i++){   
            if(num<a[i]) 
                continue;  
            while(num>=a[i]){  
                num-=a[i];  
                s1+=b[i];  
            }  
              
        }  
        return s1;   
    }
};
```
## 总结体会：
我们发现这里面有个麻烦的点，数字可以放在左边也可以放在右边。如果都只能放在右边，那样就可以直接使用加法。如9表示为 IX, 而如果表示为 VIIII,这样处理相加就OK。这样的话我们来先把符号和对应数字分别表示出来，在慢慢判断数字大小，把对应的数字的字符加入到s1字符串中。