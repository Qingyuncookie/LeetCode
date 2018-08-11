# 问题
给定一个数组，其中每个元素的值代表当天购买股票的价格，只买一股卖一股的情况下，设计算法找到获利最大的买卖方法。
# 代码
```python
class Solution(object):
    def maxProfit(self, prices):
        max_profit, min_price = 0, float('inf')
        for price in prices:
            min_price = min(min_price, price)
            profit = price - min_price
            max_profit = max(max_profit, profit)
        return max_profit

```
# 总结
for in是Python中的for循环语句。float('inf')表示无限大。
