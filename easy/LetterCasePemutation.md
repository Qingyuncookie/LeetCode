# 问题
给定一个字符串S，我们可以将其中的一个或多个小写字母变为大写来生成新的字符串，求能得到的左右字符串的列表。
# 代码
```c
void permute (string S, vector<string>& result, int index)
{
  result.push_back(S);
  if(index>=S.size()) return;
  for(int i =index;i<S.size();i++)
  {
    if(isalpha(S[i]))
    {
      S[i]^=32;
      permute(S, result, i+1)；
      S[i]^=32;
    }
  }
}

vector<string> letterCasePermutation(string S)
{
  vector<string>result;
  permute(S, result, 0);
  return result;
}
```
# 总结
isalpha()函数,用于检查是否是英文字母，除此之外还有isnum()等。
注意S[i]^=32,这一步将小写转换成为大写，再进行一次异或则回到原值。
使用迭代的方法。
