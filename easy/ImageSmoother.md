#　问题
给定一个二维整数算子M来代表一幅图像的灰度级，设计一个平滑滤波使得每一个单元格的灰度值变为每一个中心元素以及周围八个元素的平均值。如果周围的单元格小于８个，则使用尽可能多的单元格。
#　代码
```c
vector<vector<int>> imageSmoother(vector<vector<int>>& M)
{

    int dir[8][2] = {{0,1},{0,-1},{1,0},{-1,0},{1,1},{-1,-1},{1,-1},{-1,1}};
    vector<vector<int>> ans(M.size(),vector<int>(M[0].size()));
    for(int i = 0; i < M.size(); i++)
    {
        for(int j = 0; j < M[0].size(); j++)
        {
            int cnt = 1; ans[i][j]+= M[i][j];
            for(int k = 0; k < 8; k++)
            {
                int xx = i+dir[k][0];
                int yy = j+dir[k][1];
                if(xx < 0 || yy < 0 || xx >= M.size() || yy >= M[0].size()) continue;
                cnt++;
                ans[i][j] += M[xx][yy];
            }
            ans[i][j] /= cnt;
        }
    }
    return ans;

}
```
#　总结
在角上的元素，即(0,0),(0,2),(2,0),(2,2)其周围最多只有三个元素，每条边中间的位置(0,1),(1,0),(1,2),(2,2)其周围最多有五个元素，中心位置则最多有八个元素。
