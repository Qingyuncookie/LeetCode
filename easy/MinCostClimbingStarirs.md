# 问题
爬楼梯损失最少的问题，每一层有不同花费，求爬到楼顶损失最少的方法。
# 代码
```c
int minCostClimbingStairs(vector<int>& cost)
{
    int n = cost.size();
    vector<int> dp(n,0);
    dp[0] = cost[0];
    dp[1] = cost[1];
    for (int i = 2; i < n; i++)
        dp[i] = cost[i] + min(dp[i-1],dp[i-2]);
    return min(dp[n - 1], dp[n - 2]);  
}
```
# 总结
斐波那契数列问题，以及动态规划问题。
