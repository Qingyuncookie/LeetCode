# 问题
  给定一些具有特定含义的字符，分别代表一些相应的操作。
# 代码
```c
int calPoints(vector<string>& ops)
{
    stack<int>stack;
    for(int i=0;i<ops.size();i++)
    {
        if(ops[i]=="+")
        {
            int n=stack.top();
            stack.pop();
            int m=stack.top();
            stack.pop();

            stack.push(m);
            stack.push(n);
            stack.push(m+n);
        }
        else if(ops[i]=="D")
        {
            int h=stack.top();
            stack.push(h*2);
        }
        else if(ops[i]=="C")
        {
            stack.pop();
        }
        else
        {
            int t;
            stringstream ss;
            ss<<ops[i];
            ss>>t;
            stack.push(t);
        }
    }
    int sum=0;
    while(!stack.empty())
    {
        sum+=stack.top();
        stack.pop();
    }

return sum;
}
```
# 总结
1.使用栈模拟操作。2.注意第一个if，先push m,栈的特性，先进后出。3.stringstream用来进行字符串和不同类型转换。
