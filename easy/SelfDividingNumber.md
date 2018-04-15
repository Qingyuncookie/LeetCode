# 问题
找出给定范围内所有的自整除数字。
# 代码
```c
vector<int>res;
for(int i=left,n=0;i<=right;++i)
{
    for(n=i;n>0;n/=10)
    {
        if (n%10==0||i%(n%10)!=0)
            break;
    }
    if (n==0) res.push_back(i);
}
return res;
```
# 总结
自整除数字：可以整除自身每一位上的数字。
n%10：除后取余；
int n/10:除后取整；
