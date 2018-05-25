# 问题
给定一个字符串，计算字符串中有几个回文字符串。
# 代码
```c
int countSubstrings(string s)
{
    int n=s.size(),sum=0;
    for(int i=0;i<n;++i)
    {
        for(int j=0;i-j>=0;++j)
        {
            if(s[i-j]==s[i+j]) ++sum;
            else break;
        }
        for(int j=0;i-j>=0;++j)
        {
            if(s[i+j]==s[i-j-1]&&(i-j-1)>=0&&(i+j<n)) ++sum;
            else break;
        }
    }
  return sum;  
}
```
# 总结
选中一个数往两边遍历。分为两种情况，偶数个数和奇数个数。
