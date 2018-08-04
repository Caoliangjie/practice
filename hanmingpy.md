# Practice
汉明距离
## 问题分析：
#### 
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。
## 编程实现：
```Python
class Solution(object):
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        return bin(x ^ y).count('1')##直接统计x异或y的之间1的区别，比较简单。
```
## 总结体会：
按位异或，返回是1的个数，bin来返回一个int类型的数。