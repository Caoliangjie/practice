# Practice
猜数字游戏
## 问题分析：
#### 
你正在和你的朋友玩 猜数字（Bulls and Cows）游戏：你写下一个数字让你的朋友猜。每次他猜测后，你给他一个提示，告诉他有多少位数字和确切位置都猜对了（称为“Bulls”, 公牛），有多少位数字猜对了但是位置不对（称为“Cows”, 奶牛）。你的朋友将会根据提示继续猜，直到猜出秘密数字。
请写出一个根据秘密数字和朋友的猜测数返回提示的函数，用 A 表示公牛，用 B 表示奶牛。
请注意秘密数字和朋友的猜测数都可能含有重复数字。
## 编程实现：
```C++
class Solution {
public:
    string getHint(string secret, string guess) {
       int A=0,B=0;
        int len=secret.size();
        int num[10]={0};
        for(int i=0;i<len;i++){
            if(secret[i]==guess[i]){
                A++;
            }
            else{
               num[guess[i]-'0']++;
            }
        }
        for(int i=0;i<len;i++){
           if(secret[i]!=guess[i] && num[secret[i]-'0']>0){
               num[secret[i]-'0']--;
               B++;
           }
        }
        char result[128] = {0};  
        sprintf(result,"%dA%dB",A, B);  
        return result;
    }
};
```
## 总结体会：
A代表数字正确且位置正确的个数 ，B代表数字正确但位置不正确的个数。我们进行两次遍历，第一次找数字正确且位置正确的(剩下的要么是数字正确但位置不正确的，要么是数字不正确位置也不正确的)，用一个数组记录guess中与secret不同的字符。第二次遍历就在剩下两种情况中找数字正确但位置不正确的，记录数组如果表示存在secret中字符，那么就是数字正确但位置不正确。