# 问题
给定一个数组，找出三个数字所能得到的最大值并输出。
# 代码
```c
int maximumProduct(vector<int>& nums)
{
    int n=nums.size();
    sort(nums.begin(), nums.end());
    int maxproduct=max(nums[n-1] * nums[n-2] * nums[n-3],nums[0] * nums[1] * nums[n-1]);
    return maxproduct;
}
```
# 总结
注意数组中可能有负数，首先sort排序，分情况计算取较大值。
