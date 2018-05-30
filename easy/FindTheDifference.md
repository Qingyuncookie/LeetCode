# 问题
给定两个只含小写字母的字符串s和t。t比s多出一个字符，找出这个字符。
# 代码
```c
char findTheDifference(string s, string t)
{
    int sum=0;
    char ch;
    if(s.size()>t.size()) swap(t,s); //s is the small one
    for(int i=0; i<s.size(); i++)
    {
        sum-=(s[i]);
        sum+=(t[i]);
    }
    sum+=(t[s.size()]);
    ch=(char)(sum);
    return ch;

}
```
# 总结
利用字母实际是ASCII码，将其转换为十进制最后再转换为字母。
