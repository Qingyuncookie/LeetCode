# 问题
给定两个数组，写一个函数计算他们的交集。
# 代码
```c
vector<int> intersection(vector<int>& nums1, vector<int>& nums2)
{
    set<int> set1(nums1.begin(),nums1.end());
    set<int> set2(nums2.begin(),nums2.end());
    vector<int> result;
    for(auto i :set1)
    {
        if(set2.find(i)!=set2.end()) result.push_back(i);
    }
    return result;

}
```
# 总结
注意：在结果中每一个元素都是唯一的。结果无顺序要求。
先将num中的数存入set中，而set可用于检查一个数组中的元素是否在另一个数组中出现。而且set可以自动去重。
