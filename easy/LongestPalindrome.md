# 问题
给定一个字符串包含大写字母和小写字母,找出用这些字母所能建立的最长的回文字符串.
# 代码
```c
int longestPalindrome(string s)
{
  int count=0;
  vector<int> array(130,0);
  for(char a:s)
  {
    array[a]++;
  }
  int flag=0;
  for(int a:array)
  {
    if(a%2==0)
    {
      count+=a;
    }
    else if(a%2==1)
    {
      flag=1;
      if(a>1)
      {
        count +=(a-1);
      }
    }
  }
  if(flag) count++;
  return count;
}
```
# 总结
只要出现一次单数,则flag置1,最后加一个单数.
