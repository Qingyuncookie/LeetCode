# 问题
根据给定的所有员工信息（员工id，importance值，所有直属下属的id）和某个员工的id，求得这个员工及其下属的总的importance值。
# 代码
```c
{
  unordered_map<int, Employee*> m;
queue<Employee*>              q;
public:
int getImportance(vector<Employee*> employees, int id)
{
int result = 0;

for (auto e : employees)
{
    m[e->id] = e;
}

q.push(m[id]);

while(!q.empty())
{
    Employee * e = q.front();
    q.pop();
    result += e->importance;
    for (auto sub : e->subordinates)
    {
        q.push(m[sub]);
    }
}
return result;
}
'''
# 总结
采用递归实现。
