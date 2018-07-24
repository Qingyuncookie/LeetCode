# 问题
给定一个字符串模式，判断后面的字符串是否和前面的字符串有相同的模式。

# 程序
```C
bool wordPattern(string pattern, string str) {
        map<char,string> map1;
        map<string,char> map2;
        int left=0,right=0;
        for(int i = 0 ;i<pattern.size(); i++){
            while(right<str.size()&&str[right]!=' ') right++;
            if(right==left) return false;
            string tmpStr = str.substr(left,right-left);
            if(map1.find(pattern[i])!=map1.end()){
                if(map1[pattern[i]]!=tmpStr) return false;
            }else if(map2.find(tmpStr)!=map2.end()){
                if(map2[tmpStr]!=pattern[i]) return false;
            }else{
                map1[pattern[i]] = tmpStr;
                map2[tmpStr] = pattern[i];
            }
            left = ++right;
        }
        if(right<str.size()) return false;
        return true;
    }
```
# 总结
注意map的使用，map提供的是一种键值对容器，里面的数据都是成对出现的，每一对中的第一个值称之为关键字(key)，每个关键字只能在map中出现一次，第二个称之为该关键字的对应值。
