# 问题
字符串反转。
# 代码
```c
string reverseString(string s)
{
     return string(s.rbegin(),s.rend());
}
```
# 总结
rbegin()返回一个逆向迭代器，指向字符串的最后一个字符。
