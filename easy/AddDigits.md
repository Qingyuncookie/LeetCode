# 问题
给定一个非负整数，将其每一位上的数字相加，重复进行，直到最后剩一位数字。
# 代码
```c
int addDigits(int num)
{
    int res=num;
    while(res>=10)
    {
        res=(res/10)+(res%10);
    }
    return res;
}
```
# 总结
第一次自已独立完成的代码，可以不用定义res,直接对num进行运算。
