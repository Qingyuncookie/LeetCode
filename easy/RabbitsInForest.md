# 问题
假设一个森林里有若干只小兔子，每只兔子都有颜色。现在这群兔子里的其中几只兔子会告诉你除它自己以外与它颜色相同的兔子有多少个，现在要求根据几只兔子的回答求出森林里最少有几只兔子（有些兔子并未回答）。
# 代码
```c
int numRabbits(vector<int>& answers)
{
    unordered_map<int, int> hash;  
    for (auto answer : answers) {  
        ++hash[answer];  
    }  
    int ret = 0;  
    for (auto it = hash.begin(); it != hash.end(); ++it) {  
        int group_num = ceil((double)it->second / (it->first + 1));  
        ret += group_num * (it->first + 1);  
    }  
    return ret;  

}
```
# 总结
同一种颜色的兔子的答案一定是相同的（但是答案相同的兔子不一定就是一种颜色），答案不同的兔子一定颜色不同。所以我们的思路就是首先把答案相同的兔子进行聚类。对于每组答案相同的兔子而言，如果它们都属于同一种颜色，那么参与回答的兔子数量一定不会超过它们的答案+1。根据这一限制，我们就知道回答这组答案的兔子的颜色数的最小可能，而每种颜色的兔子的个数即是它们的答案+1，这样就可以得到回答这组答案的兔子的最小可能颜色数。这样把所有组答案的兔子的最小可能个数加起来，就是题目所求。
