# 问题
给定一串非空整数序列，除其中一个整数其余均出现两次，设计一个线性时间算法，并且不需要额外空间，找出这个整数。
# 代码
```c
int singleNumber(vector<int>& nums)
{
 int num = 0,n=nums.size();
 for (int i = 0; i < n; ++i)
 {
     num ^= nums[i];
 }
 return num;
}
```
# 总结
利用相同数字异或为0的特点，将序列中所有数字异或后，剩余数字即为仅出现一次的数字。
