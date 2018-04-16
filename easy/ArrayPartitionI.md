# 问题
数组分割问题，两两一组，使得每一组中最小数字之和最大。
# 代码
```c
int arrayPairSum(vector<int>& nums)
{
   int res=0,n=nums.size();
    sort(nums.begin(),nums.end());
    for(int i=0;i<n;i+=2)
    {
        res+=nums[i];
    }
   return res;     
}
```
# 总结
1.要最大化每组数的最小值之和，必须要使同组两个数差距最小，即给数组排序，按顺序两两一对。
2.sort(),排序函数，在括号内表示一个范围，sort(begin,end).
