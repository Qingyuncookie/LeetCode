# 问题
给定一个非空整数序列,找到前K个出现次数最多的元素。
# 代码
```c
vector<int> topKFrequent(vector<int>& nums, int k)
{
    unordered_map<int,int> map;
    for(int num : nums){
        map[num]++;
    }

    vector<int> res;
    priority_queue<pair<int,int>> pq;
    for(auto it = map.begin(); it != map.end(); it++){
        pq.push(make_pair(it->second, it->first));
        if(pq.size() > (int)map.size() - k){
            res.push_back(pq.top().second);
            pq.pop();
        }
    }
    return res;

}
```
# 总结
unordered_map的应用。
