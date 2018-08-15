# Practice
Pascal's Triangle II
## 问题分析：
#### 
Given a non-negative index k where k ≤ 33, return the kth index row of the Pascal's triangle.
Note that the row index starts from 0.
## 编程实现：
```C++
class Solution:
    def getRow(self, rowIndex):
        rownum=rowIndex+1
        currow=[1]
        if rownum==1:
            return currow
        if rownum>0:
            currow=[1]
            for index in range(rownum):
                prerow=currow
                currow=[1]
                for j in range(index-1):
                    currow.append(prerow[j]+prerow[j+1])
                currow.append(1)
        return currow
```
## 总结体会：
我们发现杨辉三角除了第一个和最后一个数字之外，其他的数字都是上一行左右两个值之和。那么我们只需要两个for循环，除了第一个数为1之外，后面的数都是上一次循环的数值加上它前面位置的数值之和，不停地更新每一个位置的值，便可以得到第n行的数字。