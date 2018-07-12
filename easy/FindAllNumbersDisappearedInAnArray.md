# 问题
给定一个整数数组，其中有n个值，最大的元素不超过n,且所有元素不小于1，一些元素出现两次，其余的均出现一次，找出（1，n)中所有未出现的数字。
# 代码
```c
vector<int> findDisappearedNumbers(vector<int>& nums)
{
  vector<int> result;
  for(int i=0;i<nums.size();i++)
  {
    int index=abs(nums[i])-1;
    if (nums[index]>0) nums[index] = -nums[index];
  }
  for(int i=0;i<nums.size();i++)
  {
    if(nums[i]>0)
    {
      result.push_back(i+1);
    }
  }
  return result;
}
```
# 总结
将数组的内容与序号做匹配，内容-1成为新的序号，将此序号下的内容置为负数，若已经为负数则保持不变。没有置为负数的内容其序号+1即为没有出现过的数字。
