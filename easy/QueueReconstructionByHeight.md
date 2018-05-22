# 问题
给定一个对列，里面的人杂乱无章，每个人由一对整数值（h,k)代表，h表示人所在的高度，k表示此人同高度或更高高度的人的总数。
# 代码
```c
vector<pair<int, int>> reconstructQueue(vector<pair<int, int>>& people)
{
 auto comp = [](const pair<int, int>& p1, const pair<int, int>& p2)
 {
    return p1.first > p2.first || (p1.first == p2.first && p1.second < p2.second);
 };
 sort(people.begin(), people.end(), comp);
 vector<pair<int, int>> res;
 for (auto& p : people)
    res.insert(res.begin() + p.second, p);
 return res;
}
```
# 总结
auto comp是建立一个排序的方法，首先按h从大到小排列，k从小到大排列。
sort(begin,end,comp)意为按comp的排序机制从头到尾排列。
insert（res.begin（）+ n,p)是在res中将p插入第n个元素前。
for(auto& p : people)意为遍历people。
