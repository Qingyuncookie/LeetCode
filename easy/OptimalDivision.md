# 问题
给定一串正整数，相邻数字之间加除号“/”转化为字符型，并加一个括号使其得到最大值。
# 代码
```c
string optimalDivision(vector<int>& nums)
{
    if (nums.empty()) return "";
    string res = to_string(nums[0]);
    if (nums.size() == 1) return res;
    if (nums.size() == 2) return res + "/" + to_string(nums[1]);
    res += "/(" + to_string(nums[1]);
    for (int i = 2; i < nums.size(); ++i)
    {
        res += "/" + to_string(nums[i]);
    }
    return res + ")";   
}
```
# 总结
此算法的重点在于如何得到最大值，经过观察发现，第一个数字只能作为被除数，第二个数字只能作为除数，若想得到最大值，其余数字全部作为乘法因子，因此给第二个数字直到最后一个数字加括号。
