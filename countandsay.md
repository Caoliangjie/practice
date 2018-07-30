# Practice
数数并说
## 问题分析：
#### 
报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。其前五项如下：
1.     1
2.     11
3.     21
4.     1211
5.     111221
## 说明：
1 被读作  "one 1"  ("一个一") , 即 11。
11 被读作 "two 1s" ("两个一"）, 即 21。
21 被读作 "one 2",  "one 1" （"一个二" ,  "一个一") , 即 1211。

给定一个正整数 n ，输出报数序列的第 n 项。

注意：整数顺序将表示为一个字符串。
## 编程实现：
```python
class Solution:
    def countAndSay(self, n):
        """
        :type n: int
        :rtype: str
        """
        S="1"
        for i in range(1,n): 
            S=self.myfun(S)#f返回上一个数变化的值。
        return S
    def myfun(self,S):
        res=""##清空初始
        dict={}
        for s in S: 
            if len(dict) is 0:
                dict[s]=1  ##记录数值为1?
            else: 
                if s not in dict.keys():##为0的时候
                    name = list(dict.keys())[0]##返回一个字典所有的键值
                    count = dict[name]##count负责记住这个数字的数目
                    res += str(count) + str(name)##用字符串进行链接
                    del dict[name] #紧接着把上一个数删除。
                    dict[s] = 1##
                else:
                    dict[s]+=1##没有的话
        if len(dict) is 1:    
            name = list(dict.keys())[0]
            count = dict[name]
            res += str(count) + str(name)##记录
        return res
```
## 总结体会：
注释中写的也较为详细，这里分开两端函数，一方面是为了循环的方便，另一方面也是保证对应过程清晰。