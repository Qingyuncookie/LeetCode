# 问题
给定一个排列模式和一个字符串,,判断这个字符串是否以给定模式排列.
# 代码
```c
bool wordPattern(string pattern, string str)
{
  string s;
  vector<string> v;
  stringstream ss(str);
  while(ss>>s)
  {
    v.push_back(s);
  }
  if(pattern.length()!=v.size()) return 0;
  string p;
  for(int i=0;i<v.size();i++)
  {
      p+=v[i];
  }
  unordered_map<string,char> m1;
  unordered_map<char,string> m2;
  for(int i=0;i<v.size();i++)
  {
      m1.insert({v[i],pattern[i]});
      m2.insert({pattern[i],v[i]});
  }
  string a,b;
  for(int i=0;i<v.size();i++)
  {
      a+=m1[v[i]];
      b+=m2[pattern[i]];
  }
  if(a==pattern&&b==p)
      return 1;
  return 0;
}
```
# 总结
将模式和字符串利用unorderset_map做了一个映射处理.
