# 问题
给定两个字符串A和B，判断A是否能通过循环移位变成B.
# 代码
```c
bool rotateString(string A, string B)
{
    if(A.size()!=B.size()) return false;
    if(A.empty()&&B.empty()) return true;
    for(int i=0;i<A.size();i++)
    {
        A.append(1, A[0]);
        A=A.substr(1);
        if(A==B) return true;
    }
    return false;
}
```
# 总结
A.append(1,A[0])表示添加A[0]开始A的“1”个数。substr()截取一个字符串。A.substr(1)表示截取第一位之后的字符串。
