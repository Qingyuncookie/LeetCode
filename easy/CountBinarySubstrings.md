# 问题
给定一个01二进制字符串，看有多少个包含0和1数目相同的子字符串，而且0和1必须是连续的。
# 代码
```c
int countBinarySubstrings(string s)
{
    int curLen = 1, prevLen = 0, cnt = 0;
    for (int i = 1; i < s.size(); i++)
    {
        if (s[i] == s[i - 1]) curLen++;
        else
        {
           prevLen = curLen;
           curLen = 1;
        }
        if (prevLen >= curLen) cnt++;
    }
    return cnt;    

}
```
# 总结
curlen记录连续符号的个数，不相等了则curlen置1，重新记录下一符号相连的个数，并且在下一符号的个数尚未比上一个符号个数多时，总的个数加1.
