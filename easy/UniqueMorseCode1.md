# 问题
  摩斯码用 ._ 元素来表示英文26个字母，给你一些单词，判断这些单词中含几种摩斯码形式。
# 代码
```C
int uniqueMorseRepresentations(vector<string>& words)
{
  vector<string> m{".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."};
  unordered_set<string> s;
    for(string x: words)
      {           
         string t="";
         for(char c: x)
            t+=m[c - 'a'];
         s.insert(t);
      }
  return s.size();
 }
```
# 总结
利用unordered_set叫是无序集合容器的特点，计算种类数的多少。
