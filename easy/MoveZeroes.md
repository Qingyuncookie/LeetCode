# 问题
给定一个数组，写一个函数将其中所有的0放在数组最后，同时保持非0元素的相对顺序。
# 代码
```c
void moveZeroes(vector<int>& nums)
   {
      if(nums.size()<2) return;
      int count = 0;
      for(int i=0; i<nums.size(); i++)
      {
        if(nums[i]==0) count++;
        else swap(nums[i-count], nums[i]);
      }
      return;
    }
```
# 总结
swap:交换,遇到0,count++,其余不发生变化，遇到不是0的数字，跟第一个0交换位置。我们的第一想法是将0放在后面，而这个函数的想法是将不是0的数字跟最前面一个0交换，将其放在前面，且不改变原来的顺序。
