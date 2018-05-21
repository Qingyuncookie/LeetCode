# 问题
根据日常气温列表，制作一个列表，给出以后的天气中比今天温度高需要等待的天数。
# 代码
```c
int n = temperatures.size();  
vector<int> ret(n, 0);  
stack<pair<int, int>> s;  
for (int i = 0; i < n - 1; ++i) {  
    if (temperatures[i] < temperatures[i + 1])
    {  
        ret[i] = 1;  
        while (!s.empty() && temperatures[i + 1] > s.top().first)
        {  
            ret[s.top().second] = i + 1 - s.top().second;  
            s.pop();  
        }   
    }   
    else s.push(make_pair(temperatures[i], i));  
}  
return ret;  
```
# 总结
pair的主要作用是将两个数据合并为一个数据，两个数据可以为相同类型也可以为不同类型，此处是将两个int类型合并为一个。
将pair中的两个值，当天的温度和当天的天数放入s中。
