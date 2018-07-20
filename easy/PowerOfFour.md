#问题
给定一个整数，判断其是否为4的次方数。
#代码
```c
bool isPowerOfFour(int num)
{
    while(num&&num%4==0)
    {
        num/=4;
    }
    return num==1;
}
```
#总结
while(num)意为当num!=0时条件成立.
return num==1意为当num=1时返回true，不等时返回false。
