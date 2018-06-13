# 问题
有两个包含餐馆名的数组，求他们共有的最小下标和的餐馆名称。
# 代码
```c
vector<string> findRestaurant(vector<string>& list1, vector<string>& list2)
{
    int min_sum = list1.size() + list2.size();
    unordered_map<string, int> sum;
    vector<string> answer;
    for (int i = 0; i < list1.size(); ++i) sum[list1[i]] = i+1;
    for (int i = 0; i < list2.size(); ++i)
    {
        if (sum.find(list2[i]) != sum.end())
        {
            sum[list2[i]] += i+1;
            min_sum = min(sum[list2[i]], min_sum);
        }
    }
    for(int i = 0; i < list1.size(); ++i)
    {
        if(sum[list1[i]] > i+1 and sum[list1[i]] == min_sum) answer.push_back(list1[i]);
    }
    return answer;

}
```
# 总结
首先遍历一遍数组，并用map记录下元素的下标。当发现相同元素师记录下元素下表和并与minmum作对比，同时sum更新为[元素，下表和]的形式。
