# 问题
width为26个元素,每个代表a-z的长度。对应字符串s,一行最多可以放100。计算行数以及最后一行长度。
# 代码
```c
vector<int> numberOfLines(vector<int>& widths, string S)
{
    if(S.length()==0) return {0,0};
    int line_count=1,char_count=0;
    for(auto c : S)
    {
        int width=widths[c - 'a'];
        if (char_count+width<=100) char_count+=width;
       else
      {
        ++line_count;
        char_count=width;

      }
    }
    return{line_count,char_count};
}
```
# 总结
1.最后一个字母在此行放不下，另辟一行。2.width中按照26字母顺序排列，直接使用S[i] - ‘a’的方式即可获得相应字母在widths中的索引。
