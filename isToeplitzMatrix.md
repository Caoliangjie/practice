# Practice
Toeplitz Matrix
## 问题分析：
#### 
A matrix is Toeplitz if every diagonal from top-left to bottom-right has the same element.
Now given an M x N matrix, return True if and only if the matrix is Toeplitz.
## 编程实现：
```C++
class Solution {
public:
    bool isToeplitzMatrix(vector<vector<int>>& matrix) {
        int m = matrix.size() ;
        int n = matrix[0].size() ;
        for(int i = 0 ; i < m-1 ; i++){
            for(int j = 0 ; j < n-1 ; j++){
                if (matrix[i][j] != matrix[i+1][j+1])
                    return false ;
            }
        }
        return true ;
    }
};
```
## 总结体会：
如果数组中每一个对角线上的元素都相等，则返回true。那我们就按照要求进行遍历即可，题目看上去复杂，实际仔细阅读会发现比较简单。