# 问题
给定一个只含小写字母的字符串,其中的字母是具有相同特征的连续组合.如果有三个以及三个以上的连续特征,则称为大组合,找出所有大组合的起始位置.
# 代码
```c
vector<vector<int>> largeGroupPositions(string s)
{
  vector<vector<int>> res;
  int left=0;
  int right=left+2;
  while(left<s.size()&&right<s.size())
  {
    if(s[left]!=s[left+1])||s[left]!=s[left+2])
    {
      left++;
    }
    else
    {
      while(right<s.size()&&s[right]==s[left])
      {
        right++;
      }
      res.emplace_back(vector<int>{left,right-1});
      left=right;
    }
    right=left+2;
  }
  return res;
}
```
# 总结
emplace_back 添加新元素到容器尾.首先判断连续三个元素是否相等,若不满足条件则left+1继续判断,若满足条件则right+1继续判断是否第四个依然相等.
