# 问题
给出0-n中的n个数字，找到其中缺少的那一个。
# 代码
```c
int missingNumber(vector<int>& nums)
{
    int n = nums.size();  
    int expect = (n+1) * n / 2;  
    for(int i = 0; i < n; i ++)  
        expect -= nums[i];  
    return expect;  

}
```
# 总结
对数列求和，逐项减掉已有的数字，剩下的便是缺失的数字。
