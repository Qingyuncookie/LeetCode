# 问题
A多于两个或者L连续三个及以上，则不通过。
# 代码
```c
bool checkRecord(string s)
    {
        int num=0,cnum=0;
        for(int i=0;i<s.size();++i)
        {
            if(s[i]=='A')
            {
                num++;
                cnum=0;
            }
            else if(s[i]=='L') cnum++;
            else cnum=0;
            if(num>=2||cnum>2) return false;
        }
        return true;
    }
```
# 总结    
注意是连续三个L出现。
