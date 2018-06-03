# 问题
给定两个整数，计算它们的和。不允许使用“+”或”-”运算符。
# 代码
int getSum(int a, int b) {
    int res = a ^ b;
    int c = a & b;
    if(c == 0) return res;
    return getSum(res, c<<1);
 }
# 总结
'^'异或运算符，‘&’与运算符。如果c=0,返回异或值，即和值。如果c!=0,则进行递归运算。
