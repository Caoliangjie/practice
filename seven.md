# Practice
七进制数
## 问题分析：
#### 
给定一个整数，将其转化为7进制，并以字符串形式输出。
##注意:
 输入范围是 [-1e7, 1e7] 。
## 编程实现：
```C++
class Solution {  
public:  
    string convertToBase7(int num) {  
        string ans;  
        if(num==0)  
            return "0";  
        bool l;  
        if(num>0)  
            l= 0;  
        else  
            l= 1;  
        num=abs(num);  
        while(num)  
        {  
            ans+=to_string(num%7);  
            num /= 7;  
        }   
        for(int i=0;i<ans.size()/2;i++)  
        {  
            swap(ans[i],ans[ans.size()-i-1]);  
        }  
        if(l==1)  
            ans.insert(ans.begin(),'-');  
        return ans;  
    }  
};  
```
## 总结体会：
首先这里的想法是得用字符串，因为范围这部分比较大说实话，然后就是看看是正负，然后运用公式，十进制模7，得到的数放入ans字符串中，最后如果是负数在首部加上负号。