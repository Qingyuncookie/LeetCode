# 问题
一个偶数长度的数组，不同数字代表不同类型的糖果，将糖果分成数量相等的两份给哥哥妹妹，问妹妹最多分到几种类型的糖果。
# 代码
```c
int distributeCandies(vector<int>& candies)
{
    unordered_set<int> candyType(candies.begin(), candies.end());
    return min(candyType.size(),candies.size() / 2);  

}
```
# 总结
设糖果总数为N，种类为M,妹妹分得的糖果数量为N/2，为了使妹妹得到的种类数最多，优先将每个种类的糖果分一个给妹妹。如果N/2 >= M , 妹妹每种糖果都可以拿到一个，如果N/2 < M，妹妹最多只能拿到N/2种糖果。
