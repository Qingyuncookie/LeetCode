# 问题
给定一个正整数，求其补码。
条件：1.给定的整数在32位有符号整数范围内。2.假定整数的二进制表示中没有前导零位。
# 代码
```c
int findComplement(int num)
{
    bool start = false;
    for (int i = 31; i >= 0; --i) {
        if (num & (1 << i)) start = true;
        if (start) num ^= (1 << i);
    }
    return num;
}
```
# 总结
1.&：按位与。2.<<二进制左移运算符。3.翻转的起始位置从最高位的1开始，0不能被翻转。
