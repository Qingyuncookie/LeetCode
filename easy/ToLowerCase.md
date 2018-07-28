# 问题
给定一个字符串，将气转换成全小写字符串。
# 代码
```c
string tolowercase(string str)
{
  for(char& c : str)
  {
    if(c>=‘A’ && c<='Z') c+=32;
  }
  return str;
}
```
# 总结
在计算机中ASCII码与字母对应，ASCII码中小写字母比大写字母大32，因此可以直接通过数字的加减完成大小写的转换。
