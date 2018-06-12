# 问题
判断使两个字符串相等需要删掉的字符的ASII码的值的和。
# 代码
```c
int minimumDeleteSum(string s1, string s2)
{
    int m = s1.size(), n = s2.size();
    vector<vector<int>> dp(m+1, vector<int>(n+1, 0));

    for (int i = 1; i <= m; i++)
        dp[i][0] = dp[i-1][0]+s1[i-1];
    for (int j = 1; j <= n; j++)
        dp[0][j] = dp[0][j-1]+s2[j-1];

    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            int a;
            if (s1[i-1] == s2[j-1]) a=0;
            else  a=s1[i-1]+s2[j-1];
            dp[i][j] = min(dp[i-1][j-1]+a,min(dp[i-1][j]+s1[i-1], dp[i][j-1]+s2[j-1]));
        }
    }
    return dp[m][n];
}
```
# 总结
双线程操作。
