# 问题
给定一个十进制整数，转换为七进制数。
# 代码
```c
if (num == 0) return "0";
vector<char> base7;
bool isnegative = false;
if (num < 0)
{
    num = -num;
    isnegative = true;
}       
while (num > 0)
 {
    base7.push_back(num % 7+'0'-0);
    num /= 7;
}
if (isnegative)
    base7.push_back('-');
return string(base7.rbegin(), base7.rend());
```
# 总结
首先要清楚进制之间的转换方式。
