# 问题
常对角矩阵：矩阵中每条自左上至右下的斜线上的元素相同。给定M×N矩阵，如果是常对角矩阵，则返回true。
# 代码
```c
bool isToeplitzMatrix(vector<vector<int>>& matrix)
{
    int m=matrix.size(),n=matrix[0].size();
    for(int i=0;i<m-1;i++)
    {
        for(int j=0;j<n-1;j++)
        {
            if(matrix[i][j]!=matrix[i+1][j+1]) return false;
        }
    }

   return true;
}
```
# 总结
对斜对角线上的元素进行遍历，判断是否相等，若不相等返回false，相等则继续遍历。
