# 问题
给定一串非空整数序列，其中两个整数出现一次，其余均出现两次，找到出现一次的两个整数。
# 代码
```c
vector<int> singleNumber(vector<int>& nums)
{
    int AxorB = 0;
    for(int i = 0;i<nums.size();i++){
        AxorB^=nums[i];
    }
    int mask = AxorB &(-AxorB);
    int A = 0,B = 0;
    for(int i = 0;i<nums.size();i++){
        if(mask&nums[i])
            A ^= nums[i];
        else
            B ^= nums[i];
    }

    return vector<int>({A,B});

}
```
# 总结
前半部分与SingleNumber一样进行异或运算，得到的为出现一次的两个整数的异或，因此此题的重点在于如何将两个进行异或运算的数字分开。
