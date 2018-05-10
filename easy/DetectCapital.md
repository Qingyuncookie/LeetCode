# 问题
给定一个单词，判断其大小写是否规范。
# 代码
```c
bool detectCapitalUse(string word)
{
    if(word.size()==1) return true;
    bool firstLetterIsUppercase = false;
    if (word[0] >= 'A' && word[0] <= 'Z')
    {
        firstLetterIsUppercase = true;
    }

    bool isLowercase = false;
    bool isUppercase = false;
    for (int i = 1; i<word.size(); i++)
    {
        if (word[i] >= 'a' && word[i] <= 'z') isLowercase = true;
        else isUppercase = true;
    }
    if (true == firstLetterIsUppercase && false == isLowercase && true == isUppercase) return true;
    if (false == firstLetterIsUppercase && true == isLowercase && false == isUppercase) return true;
    if (true == firstLetterIsUppercase && true == isLowercase && false == isUppercase) return true;
    return false;
}
```
# 总结
如果首字母为大写，则后面全是小写或者全是大写，书写规范。
如果首字母为小写，则后面全是小写书写规范。
