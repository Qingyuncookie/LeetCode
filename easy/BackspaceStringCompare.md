# 问题
给定两个字符串S和T，字符串中的#表示退格,遇到退格则删除前面一个有效字符,经过处理后比较两个字符是否相等.
# 代码
```c
bool backspaceCompare(string S, string T)
{
  stack<char> s, t;
  const auto apply_2_stack = [](const string& str, stack<char>& s)
  {
    for(const char c : str)
    {
      if(c=='#')
      {
        if(s.size())
        {
          s.pop();
        }
      }
      else
      {
        s.push(c);
      }
    }
  }
  apply_2_stack(S,s);
  apply_2_stack(T,t);
  if(s==t) return true;
  else return false;
}
```
# 总结
将S和T入栈,遇到#,将栈顶元素出栈,否则将其入栈.
