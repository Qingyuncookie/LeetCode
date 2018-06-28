# 问题
给定一组只含小写字母的字母组和一个目标字母，找出字母组中比给定目标字母大的最小字母。若没有，则返回字母组的第一个字母。
# 代码
```c
char nextGreatestLetter(vector<char>& letters, char target)
{
    for (auto a : letters)
    {
        if (target < a) return a;
    }
    return letters[0];  

}
```
# 总结
遍历。
