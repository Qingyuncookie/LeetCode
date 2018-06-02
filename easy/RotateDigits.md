# 问题
将一个数字的每一位旋转180度，如果跟之前的数字不一样则是有效的，统计1到N中有多少这样的数字，3,4,7旋转后是无效的。
# 代码
```c
int rotatedDigits(int N)
{  
    int count = 0;  
    for (int i = 2; i <= N; ++i)
    {  
        count += isValid(i);  
    }  
    return count;  
}  
private:  
bool isValid(int N)
{  
    // Valid if N contains at least one 2, 5, 6, 9, and no 3, 4 or 7s  
    bool validFound = false;  
    while (N > 0)
    {  
        if (N % 10 == 2) validFound = true;  
        if (N % 10 == 5) validFound = true;  
        if (N % 10 == 6) validFound = true;  
        if (N % 10 == 9) validFound = true;  
        if (N % 10 == 3) return false;  
        if (N % 10 == 4) return false;  
        if (N % 10 == 7) return false;  
        N = N / 10;  
    }  
    return validFound;  
}  
```
# 总结
注意1和10也是无效的，因为它们旋转后还是自己。
