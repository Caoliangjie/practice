# Practice
翻转图像
## 问题分析：
#### 
给定一个二进制矩阵A，我们想先水平翻转图像，然后反转图像并返回结果。
水平翻转图片就是将图片的每一行都进行翻转，即逆序。例如，水平翻转 [1, 1, 0] 的结果是 [0, 1, 1]。
反转图片的意思是图片中的 0 全部被 1 替换， 1 全部被 0 替换。例如，反转 [0, 1, 1] 的结果是 [1, 0, 0]
## 编程实现：
```C++
class Solution {
public:
    vector<vector<int>> flipAndInvertImage(vector<vector<int>>& A) {
        vector<vector<int>> ans;
        vector<int> d;
        for(int i=0;i<A.size();++ i ){
            for(int j=A[i].size()-1;j>=0;--j)
            {
                d.push_back(A[i][j]^1);
            }
            ans.push_back(d);
            d.clear();
        }
        return ans;
    }
};
```
## 总结体会：
图像矩阵存放在一个二维数组中，那么只要翻转图像矩阵的每一行，并且对每一个元素取反，就可以保证最后的图像是全部翻转的，这点一定和垂直翻转区别开来。