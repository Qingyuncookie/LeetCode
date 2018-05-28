# 问题
如果给定一个字符串和一个整数k，则需要对从字符串开头算起的每2k个字符的前k个字符进行反转。 如果还有少于k个字符，将其全部翻转。 如果小于2k但大于或等于k个字符，则反转前k个字符其余保持不变。
# 代码
```c
string reverseStr(string s, int k)
{
    int n = s.size();
    for(int i = 0; i < n; i += 2*k)
        reverse(s.begin() + i, s.begin() + min(i + k, n));
    return s;
}
```
# 总结
以2k为一个操作循环。
