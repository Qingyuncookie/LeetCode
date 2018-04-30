# 问题
给一个数组与其子集，求子集中每个数字在原数组中右边第一个较大的数字，若不存在，输出-1。以此构成新的数组。
# 代码
```c
vector<int> res(findNums.size());
for (int i = 0; i < findNums.size(); ++i) {
    int j = 0, k = 0;
    for (j=0; j < nums.size(); ++j) {
        if (nums[j] == findNums[i]) break;
    }
    for (k = j + 1; k < nums.size(); ++k) {
        if (nums[k] > nums[j]) {
            res[i] = nums[k];
            break;
        }
    }
    if (k == nums.size()) res[i] = -1;
}
return res;
}
```
# 总结
1.遍历。2.采取栈操作，建立原数组中每个元素与其右侧第一个较大值的映射，若无则取值-1，最后再直接哈希表搜索即可。
