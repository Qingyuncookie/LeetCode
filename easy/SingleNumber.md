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
引入异或运算，相同数字异或结果为零。
