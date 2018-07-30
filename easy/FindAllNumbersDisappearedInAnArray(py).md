# 问题
给定n个整数，有的出现两次其余出现一次，找出[1，n]中没有出现过的整数值。
# 代码
```python
def findDisappearedNumber(self, nums):
    n = len(nums) + 1
    nums = set(nums)
    res = []
    for i in range(1, n)
        if (i not in nums):
           res.append(i)
    return res

```
# 总结
Python中set与c++中类似，此处功能是消除重复元素。
append是将括号内元素放入前面的容器中。
在[1,n]中进行遍历，不存在就取出来。
