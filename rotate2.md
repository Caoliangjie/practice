# Practice
旋转图像
## 问题分析：
#### 
给定一个 n × n 的二维矩阵表示一个图像。
将图像顺时针旋转 90 度。
## 说明
你必须在原地旋转图像，这意味着你需要直接修改输入的二维矩阵。请不要使用另一个矩阵来旋转图像。
## 编程实现：
```C++
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
     int i=0,j=0,n=matrix.size();
     for(i=0;i<n;++i)
     {for(j=i;j<n;++j)
     {swap(matrix[i][j],matrix[j][i]);}
         reverse(matrix[i].begin(),matrix[i].end());}
    }
};
```
## 总结体会：
还是说要会观察规律，规律有时候也很管用。这里我们实验过，翻转90度的话，首先每一行的元素与行号保持一致，然后列标是翻着写的，那么我们先把这个矩阵先取转置，把行列先进行交换，之后我们将元素对称交换，用reverse指令可以加强对vector的训练。这样可以得到旋转90度的矩阵，这个对于将来图像翻转是个基础训练。