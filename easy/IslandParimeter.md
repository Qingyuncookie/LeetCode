# 问题
给定一个二维整数的方格地图，1代表陆地，0代表有水的地方。每个方格都是垂直或者水平连接的，没有斜线。被水包围的中间有一个小岛（小岛可能包含了很多个的陆地方格），小岛里没有岛中湖（内部的水和外部的水是连通的）。每个方格单元的边长都是1，各个地方都是成直角的，长度宽度不超过100，判断小岛的边长。
# 代码
```c
int islandPerimeter(vector<vector<int>>& grid)
{
    int sum=0;
    int m=grid.size(),n=grid[0].size();
    for(int i=0;i<m;i++)
        for(int j=0;j<n;j++)
            if(grid[i][j]==1)
            {
            if(i==0||grid[i-1][j]==0) sum++;
            if(i==m-1||grid[i+1][j]==0) sum++;
            if(j==0||grid[i][j-1]==0) sum++;
            if(j==n-1||grid[i][j+1]==0) sum++;
            }
    return sum;
}
```
# 总结
判断其四面是否有陆地，四面都有陆地的对周长无影响，两面有陆地的贡献周长为2，一面有陆地的贡献周长为3，四面都没有陆地的贡献周长为4。
