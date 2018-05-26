# Practice
岛屿的最大面积
## 问题分析：
#### 
给定一个包含了一些 0 和 1的非空二维数组 grid , 一个 岛屿 是由四个方向 (水平或垂直) 的 1 (代表土地) 构成的组合。你可以假设二维矩阵的四个边缘都被水包围着。

找到给定的二维数组中最大的岛屿面积。(如果没有岛屿，则返回面积为0。)
## 编程实现：
```C++
class Solution {
public:
    int dfs(vector<vector<int>>& grid, int x0, int y0){
        int n,m,sum=1;
        n=grid.size();
        m=grid[0].size();
        grid[x0][y0] = 0;
        int s[4][2]={{0,1},{0,-1},{1,0},{-1,0}};
        for(int i=0;i<4;i++){
            int x=x0+s[i][0];
            int y=y0+s[i][1];
            if(x>=0&&x<n&&y>=0&&y<m&&grid[x][y]==1)
                sum+=dfs(grid,x,y);
        }
        return sum;
    }
    int maxAreaOfIsland(vector<vector<int>>& grid) 
    {
        int maximum=0,n,m;
        n=grid.size();
        m=grid[0].size();
        for(int i=0;i<n;i++)
            for(int j=0;j<m;j++)
            {
                if(grid[i][j]==1)   
                    maximum=max(dfs(grid,i,j),maximum);
            }
        return maximum;
    }
}; 
```
## 总结体会：
这里的话是要考虑用深度搜索来做了，当搜到一个节点让其变为0，避免重复搜索。毕竟一块只有四个边，先确定边是最稳妥的，我们这样来找到上下左右中，1最多的那块的数量。最后比对再搜索的和上一次的比对，只要最大的面积。