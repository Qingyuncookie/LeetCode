# 问题
给定一个非空的整数序列，找到最小的移动距离使数组内元素值相等。
# 代码
```c
int minMoves2(vector<int>& nums)
{

   int res = 0, i = 0, j = (int)nums.size() - 1;
    sort(nums.begin(), nums.end());
    while (i < j) {
        res += nums[j--] - nums[i++];
    }
    return res;
}
```
# 总结
首先给数组排序，如果是奇数个则中间一个数字是最后的元素，如果是偶数个，则是中间两个数字中的任意一个。两边数字变成中间数字的步数，实际上就是两个数字之间的距离。
