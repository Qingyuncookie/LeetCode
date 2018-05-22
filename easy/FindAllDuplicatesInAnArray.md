# 问题
给定一个数组，数组中的数字均大于1小于数组的size,其中一些数字出现两次，剩下的均出现一次，找到出现两次的数字并记录。要求：不开辟额外的空间，且运行复杂度为O(n)级。
# 代码
```c
 vector<int> findDuplicates(vector<int>& nums)
 {
   vector<int> res;
   for(int i=0;i<nums.size();++i)
   {
     nums[abs(nums[i])-1]=-nums[abs(nums[i])-1];
     if(nums[abs(nums[i])-1>0]) res.push_back(abs(nums[i]));
   }
   return res;
 }
```
# 总结
此方法的重点在于数组中的数字均小于数组的size，因此将数组中的数字值绝对值减1后，num[i]仍然有值。此时将其值反转为相反数，若数字出现两次，则反转两次，此时反转后的值>0，因此可通过此方法判断，若反转后的数字大于0,则出现过两次，若小于0,则只出现一次。
