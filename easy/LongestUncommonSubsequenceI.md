# 问题
给定两个字符串，计算最长的非共同子序列的长度，即不能为两个字符串共同的子序列，否则返回-1；
# 代码
```c
int findLUSlength(string a, string b)
{  
    int n = a.size();
    int m = b.size();
    if(a==b)
        return -1;
    if(n>m)
        return n;
    else
        return m;
}
```
# 总结
判断字符串字符串是否相等，以及计算其长度。
