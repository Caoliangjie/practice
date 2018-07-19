# Practice
 加一
## 问题分析：
#### 
给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。
最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。
你可以假设除了整数 0 之外，这个整数不会以零开头。
## 编程实现：
```C++
class Solution:
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        j=0
        for i in range(len(digits)):
            j=j*10+digits[i]
        j+=1
        k=str(j)
        res=[]
        for i in range(len(k)):
            res.append(int(k[i]))
        return res          
```
## 总结体会：
这里因为列表相比而言操作比较简单，那么我们直接字符串转为整数，添加到列表中然后输出列表中+1后的数，也不用担心进不进位（毕竟他转成了整数进位就不用人为操心了）
