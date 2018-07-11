# practice
字符串转整数（atoi）
## 问题分析：
#### 
实现 atoi，将字符串转为整数。
在找到第一个非空字符之前，需要移除掉字符串中的空格字符。如果第一个非空字符是正号或负号，选取该符号，并将其与后面尽可能多的连续的数字组合起来，这部分字符即为整数的值。如果第一个非空字符是数字，则直接将其与之后连续的数字字符组合起来，形成整数。
字符串可以在形成整数的字符后面包括多余的字符，这些字符可以被忽略，它们对于函数没有影响。
当字符串中的第一个非空字符序列不是个有效的整数；或字符串为空；或字符串仅包含空白字符时，则不进行转换。
若函数不能执行有效的转换，返回 0。
###说明
假设我们的环境只能存储 32 位有符号整数，其数值范围是 [−231,  231 − 1]。如果数值超过可表示的范围，则返回  INT_MAX (231 − 1) 或 INT_MIN (−231) 。
## 编程实现：
```C++
class Solution {
public:
    int myAtoi(string str) {
         int begin=0;
        int end=0;
        long long Iteger=0;//数会超过int，所以存在long里。
        int i=0;
        if(str.size()<=0) 
            return 0;//判断是不是空，这样返回0。
        for(i=0;i<str.size();i++)//遍历数组，找存在的数和正负号。
        {
            if(str[i]>='0'&&str[i]<='9'||str[i]=='+'||str[i]=='-')
            {
                begin=i;//记录下来位置，跳出循环。
                break;
            }
            else if(str[i]!=' ')
            {
                return 0; //第一个非0的为空格，那么直接返回0.
            }
        }
        end=begin;//从数字或者正负号开始的地方开始。
        for(i=begin+1;i<str.size();i++)
        {
            if(str[i]<'0'||str[i]>'9')
            {
                end=i;//找到最后一个数字。
                break;
            }
        }
        if(i==str.size()) end=str.size()-1;//下面就是套路了.....计算和，有负数改为负数。
        for(i=begin;i<=end;i++)
        {
            if(str[i]>='0'&&str[i]<='9')
            {
                int tmp=str[i]-'0';
                Iteger=Iteger*10+tmp;
             if(Iteger-1>INT_MAX)
            {
                break;
            }
            }
 
        }
        if(str[begin]=='-')
        {
            if(Iteger-1>=INT_MAX)
            return INT_MIN;
            else
            return -Iteger;
        }
        else
        {
            if(Iteger>=INT_MAX)
            return INT_MAX;
            else
            return Iteger;
        }
        }
};
```
## 总结体会：
基本想法注释中也写了一些，只需要翻译出连续的数字就可以。在判断正负情况下，紧接着后面就是每一位存在的数字在当前位置乘上10的（n-1）次幂即可。超过范围的我们就输出超过范围的最大或最小数。
