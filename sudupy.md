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
class Solution:
    def isValidSudoku(self, board):
        """
        :type board: List[List[str]]
        :rtype: bool
        """
        for i in range(9):
            for j in range(9):
                if board[i][j] == '.':
                    board[i][j] = 0
        for i in range(9):
            for j in range(9):
                if board[i][j] != 0:
                    #check the board[i][j] is valid in i's row
                    for column in range(9):
                        if column != j and board[i][j] == board[i][column]:
                            return False
                    #check the board[i][j] is valid in j's column
                    for row in range(9):
                        if row != i and board[i][j] == board[row][j]:
                            return False
                    #check the board[i][j] is valid in the 3-by-3 box
                    for row in range((i // 3) * 3,(i // 3) * 3 + 3):
                        for col in range((j // 3) * 3,(j // 3) * 3 + 3):
                            if row != i and col != j and board[i][j] == board[row][col]:
                                return False
        return True
```
## 总结体会：
用三个数组，分别判断每一行，每一列，3*3的矩阵是否被修改过。因为数独固定是9*9的，那么只要保证如果一个位置被遍历过2遍，那就是说明这个数独不对。（即这个数字出现了2次。）