# 问题
给定一串单词，从中找出可以仅用美式键盘的一行字母就能键入的单词。
# 代码
```c
vector<string> findWords(vector<string>& words)
{
    set<char> row1{'q', 'w', 'e', 'r', 't', 'y', 'u', 'i', 'o', 'p'};
    set<char> row2{'a', 's', 'd', 'f', 'g', 'h', 'j', 'k', 'l'};
    set<char> row3{'z', 'x', 'c', 'v', 'b', 'n', 'm'};
    vector<set<char>> rows{row1,row2,row3};

    vector<string>validwords;
    for(int i=0;i<words.size();++i)
    {
        int row=0;
        for(int k=0;k<3;++k)
        {
            if(rows[k].count((char)tolower(words[i][0])) > 0) row=k;
        }
        validwords.push_back(words[i]);
        for(int j=1;j<words[i].size();++j)
        {
            if(rows[row].count((char)tolower(words[i][j])) == 0)
            {
                validwords.pop_back();
                break;
            }
        }
    }

  return validwords;  
  }
```
# 总结
1.tolower()函数：将所有字母换成小写。
2.set.count()判断集合中是否有此元素，有则为1，无则为0。
3.vector.push_back() 往容器尾加元素；vector.pop_back 去掉容器尾元素。
