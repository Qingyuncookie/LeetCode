# 问题
给定一串非空整数序列，除其中一个整数其余均出现两次，设计一个线性时间算法，并且不需要额外空间，找出这个整数。
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
引入异或运算，得到的数字是两个只出现一次的数字的融合，因此此方法的重点是如何将两个数字分开。
