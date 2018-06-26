# 问题
给定一个字符串，翻转每个单词中的字符顺序，空格保留，单词整体顺序不变。
# 代码
```c
string reverseWords(string s)
{
    int i=0,t=0;
    for(i=0;i<=s.size();i++)  
    {
      if(s[i]==' ' || i==s.size())
      {
          reverse(&s[t],&s[i]);
          t=1+i;
      }

    }
   return s;
}
```
# 总结
1.遇空格锁定一个单词进行反转。
2.reverse()函数的应用。注意&s[t]中的&符号。
