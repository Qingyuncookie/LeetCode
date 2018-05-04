# 问题
给定一个正整数，检查它是否有交替位：即两个相邻位总有不同的值。
# 代码
```c
bool hasAlternatingBits(int n)
{

    int pre = n & 1;  
    n = n >> 1;  
    while (n > 0)
    {  
        if ((n & 1) == pre) return false;
        pre = 1 - pre;  
        n = n >> 1;
    }
   return true;
}
```
# 总结
每次记录下n的最右边位上的值，然后再看其次右边位上的值，如果一样，返回false；如果所有相邻位都不一样，返回true。
