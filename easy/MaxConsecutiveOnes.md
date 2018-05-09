# 问题
给一个二进制数组，找出连续1最多的个数。
# 代码
```c
int findMaxConsecutiveOnes(vector<int>& nums)
{
    int res=0,sum=0;
    for(int i=0;i<nums.size();i++)
    {
        if(nums[i]==0) sum=0;
        else sum++;
        res=res>sum?res:sum;  
    }
    return res;
}
```
# 总结
遍历数组，遇到0和置0，遇1和加1.
