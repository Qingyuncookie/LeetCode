# 问题
给定一个短数组，其中一个数字出现两次，其余都出现两次，找到只出现一次的数字。
# 代码
```c
int singleNonDuplicate(vector<int>& nums)
{
      int res;
      for(int i=0;i<nums.size();i+=2)
      {
          if(nums[i]-nums[i+1] !=0)
          {
              res=nums[i];
              break;
          }
      }
    return res;
}
```
# 总结
此方法之所以能成功的原因是出现两次的数字会相邻。加入顺序打乱，则此方法并不成立。
