# Practice
三维形体的表面积
## 问题分析：
#### 
在 N * N 的网格上，我们放置一些 1 * 1 * 1  的立方体。
每个值 v = grid[i][j] 表示 v 个正方体叠放在单元格 (i, j) 上。
返回结果形体的总表面积。
## 编程实现：
```C++
class Solution {
public:
    int surfaceArea(vector<vector<int>>& grid) 
    {
        int count=0;
        int discount=0;
        for(int i=0;i<grid.size();i++)
            for(int j=0;j<grid[0].size();j++)
            {
                count+=grid[i][j];//总块数
                if(grid[i][j]>1)
                {
                    discount+=grid[i][j]-1;
                }
 
                if((j<(grid[0].size()-1))&&(grid[i][j+1]!=0))//right
                {
                    discount+=min(grid[i][j+1],grid[i][j]);
                }
 
                if((i<(grid.size()-1))&&(grid[i+1][j]!=0))//down
                {
                    discount+=min(grid[i+1][j],grid[i][j]);
                }
 
            }
        count=count*6;
        int surface=count-discount*2;
        return surface;
        
 
        
    }
};

```
## 总结体会：
先计算立方体的个数，而后计算接触面的个数，立方体*6减去接触面*2就是所求。