# Practice
Reshape the Matrix
## 问题分析：
#### 
In MATLAB, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size but keep its original data.
You're given a matrix represented by a two-dimensional array, and two positive integers r and c representing the row number and column number of the wanted reshaped matrix, respectively.
The reshaped matrix need to be filled with all the elements of the original matrix in the same row-traversing order as they were.
If the 'reshape' operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.
## Note:
The height and width of the given matrix is in range [1, 100].The given r and c are all positive.
## 编程实现：
```C++
class Solution(object):
    def matrixReshape(self, nums, r, c):
        """
        :type nums: List[List[int]]
        :type r: int
        :type c: int
        :rtype: List[List[int]]
        """
        l = []
        for i in nums:
            for j in range(len(i)):
                l.append(i[j]) 
        if r * c != len(l):
            return nums
        k = []
        for i in range(len(l)/c):
            k.append(l[i*c:(i+1)*c])
        return k
```
## 总结体会：
将一个r1xc1的矩阵重塑为rxc的矩阵，需要满足条件r1xc1=rxc的元素位置对应的关系.如果将矩阵横向展开为一维数组，元素个数为n=r1xc1 在元素在一维数组中对应的位置i： 也就是原矩阵位置[i/c1,i%c1] 新矩阵位置[i/c,i%c] 。