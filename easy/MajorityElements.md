# 问题
给定一串数组，找到数组中的多数元素，数组大小为n,其中多数元素是出现次数超过n/2的元素。
# 代码
```python
def majorityElement(self, nums):
    return sorted(num)[len(num)/2]

```
# 总结
排序之后找到中间的元素，由于多数元素始终存在且其个数大于n/2，所以排序之后中间元素一定是多数元素。
