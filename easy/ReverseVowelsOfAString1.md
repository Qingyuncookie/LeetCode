# 问题
编写一个函数，给定一个字符串，将其中的元音进行反转。
# 代码
```c
string reverseVowels(string s)
{
    vector<char> s1;
    string result;
    int j=0;
    set<char> v{'a','e','i','o','u','A','E','I','O','U'};
    for(auto& it : s)
    {
        if(v.find(it)!=v.end()) s1.push_back(it);
    }
    reverse(s1.begin(),s1.end());
    for(int i=0;i<s.size();++i)
    {
       if(v.find(s[i])!=v.end())
       {
           result.push_back(s1[j]);
           j++;
       }
       else result.push_back(s[i]);
    }
    return result;
}
```
# 总结
建立一个s1，遍历s，遇到元音便取出来放到s1中，然后将s1反转。重新建立一个空字符串，再次遍历s,若不是元音直接放入空字符串中，若是元音则从s1中取到翻转后的一个字符。
