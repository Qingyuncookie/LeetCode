# 问题
有一千个桶，只有一个桶里装的是毒药，外表看起来一样。如果一只猪喝了毒药，会在十五分钟后死亡，问至少需要多少只猪才能在一个小时内确定出哪个桶里是毒药。
# 代码
```c
int poorPigs(int buckets, int minutesToDie, int minutesToTest)
{  
    if(buckets==1) return 0;  
    int base=minutesToTest/minutesToDie+1;  
    int r=1;  
    for(int i=1;;i++)  
    {  
        r*=base;  
        if(r>=buckets)  
        return i;  
    }  
    return 0;  
}
```
#总结
每一只猪在一个小时内可检测5桶，两只猪可放到二维平面，则一个小时内可以检测25只，以此类推。
