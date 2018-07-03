# Practice
有效的数独
## 问题分析：
#### 
判断一个 9x9 的数独是否有效。只需要根据以下规则，验证已经填入的数字是否有效即可。
    1.数字 1-9 在每一行只能出现一次。
    2.数字 1-9 在每一列只能出现一次。
    3.数字 1-9 在每一个以粗实线分隔的 3x3 宫内只能出现一次。

## 编程实现：
```C++
class Solution {
public:
    bool isValidSudoku(vector<vector<char>>& board) {
        int a[9][9]={0},b[9][9]={0},c[9][9]={0};
        for(int i=0;i<board.size();++i)
            for(int j=0;j<board.size();++j)
                if(board[i][j]!='.')
                {int x=board[i][j]-'0'-1,k=i/3*3+j/3;
                 if((a[i][x])||(b[j][x])||(c[k][x]))
                    return false;
                 a[i][x]=b[j][x]=c[k][x]=1;
                }
        return true;
    }
};
```
## 总结体会：
用三个数组，分别判断每一行，每一列，3*3的矩阵是否被修改过。因为数独固定是9*9的，那么只要保证如果一个位置被遍历过2遍，那就是说明这个数独不对。（即这个数字出现了2次。）