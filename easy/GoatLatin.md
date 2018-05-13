# 问题
给定一个字符串S，由几个被空格分开的单词组成，每个单词由大写字母和小写字母组成，我们将这个句子转换成为“Goat Latin”。
规则如下：如果单词以元音开头，在单词末尾添加“ma”，如果单词以辅音开头，将第一个字母移到单词末尾并在单词末尾添加“ma”。句中的第几个单词便在单词末尾添加几个“a”。
# 代码
```c
string toGoatLatin(string S)
{
    istringstream in(S);
    string ans, word, app = "ma", table = "AEIOUaeiou";
    while (in >> word)
    {
        app += 'a';
        if (table.find_first_of(word[0]) != -1)
            ans += word + app + ' ';
        else
            ans += (word.size() == 1 ? word : word.substr(1, word.size() - 1) + word[0]) + app + ' ';
    }
    ans.pop_back();
    return ans;   
}
```
# 总结
istringstream in(S)意为将字符串S读入in中。substr意为从单词的第2个字母开始剪切word.size()-1个字母。使用while语句，每经过一个单词，app加一个'a'。
