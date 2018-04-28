# 问题
重塑矩阵，若重塑矩阵元素个数与原矩阵不符，返回原矩阵。
# 代码
```c
vector<vector<int>> matrixReshape(vector<vector<int>>& nums, int r, int c)
{
    int m = nums.size(), n = nums[0].size();
    if (m * n != r * c) return nums;
    vector<vector<int>> res(r, vector<int>(c));
    for (int i = 0; i < r; ++i)
    {
        for (int j = 0; j < c; ++j)
        {
            int k = i * c + j;
            res[i][j] = nums[k / n][k % n];
        }
    }
    return res;
}
```
# 总结
新建一个目标大小的数组，并开始遍历，对于每个位置，我们先转为拉直后的一维坐标，然后在算出在原数组中的对应位置赋值过来即可。
