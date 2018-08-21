# 问题
给定一个数组和一个值，除去数组中中给定的这个值，返回新的长度。
# 代码
```python
class Solution(object):
  def removeElement(self, nums, val):
    length = 0
    for i in xrange(len(nums)):
      if nums[i] != val:
        nums[length] = nums[i]
        length += 1
    return length

```
# 总结
设置一个length值，表示新的num数组的位置，遍历数组，如果不是val值则将其放入num[length],同时length+1.如果是val值。则不做任何变化。
