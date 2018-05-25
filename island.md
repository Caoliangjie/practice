# Practice
岛屿的周长
## 问题分析：
#### 
给定一个包含 0 和 1 的二维网格地图，其中 1 表示陆地 0 表示水域。网格中的格子水平和垂直方向相连（对角线方向不相连）。整个网格被水完全包围，但其中恰好有一个岛屿（或者说，一个或多个表示陆地的格子相连组成的岛屿）。岛屿中没有“湖”（“湖” 指水域在岛屿内部且不和岛屿周围的水相连）。格子是边长为1的正方形。网格为长方形，且宽度和高度均不超过 100 。计算这个岛屿的周长。
## 编程实现：
```C++
class Solution {  
public:  
    int islandPerimeter(vector<vector<int>>& grid) {     
        int w=grid.size();  
        int l=grid[0].size();  
        int ans=0;  
        vector<vector<int>> newl(w+2); 
        for(int i=0;i<w+2;i++)  
            newl[i].resize(l+2);  
        for(int i=1;i<w+1;i++)  
            for(int j=1;j<l+1;j++)  
                newl[i][j]=grid[i-1][j-1];                    
        for(int i=1;i<w+1;i++)  
            for(int j=1;j<l+1;j++)  
            {  
                int c=0;  
                if(newl[i][j]==1)  
                {  
                    if(newl[i-1][j] == 0)  
                        c++;  
                    if(newl[i+1][j] == 0)  
                        c++;  
                    if(newl[i][j-1] == 0)  
                        c++;  
                    if(newl[i][j+1] == 0)  
                        c++;  
                    ans+=c;  
                }  
            }  
        return ans;  
    }  
};  
```
## 总结体会：
既然这里说1是陆地，0是水域，那么我们就一步一步遍历判断，从每条边开始慢慢找存在的陆地，有陆地就记下这一边加入到ans中，最后返回ans即可。由于长宽均不超过100，所以这样遍历没有超时。