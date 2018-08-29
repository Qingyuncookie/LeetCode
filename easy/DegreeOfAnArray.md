# 问题
给定一个由非负整数构成的非空数组nums，这个序列的度被定义为人一个元素出现最高频率的频次。找到最短长度的nums的一个子串，与nums有相同的度，返回它的长度。
# 代码
```python
class Solution:
  def findShortestSubArray(self, nums):
      counts = {}
      starts = {}
      ends = {}
      max_count = -sys.maxsize
      for i, num in enumerate(nums):
          if num not in starts:
            starts[num] += 1
            ends[num] = i
            max_count = max(max_count, counts[num])
      result = sys.maxsize
      for num count in count.items():
          if count == max_count:
             result = min(result, ends[num] - starts[num] + 1)
      return result
```
# 总结
找到出现频次最多的元素的初始位置与结束位置，其减数即为最短子序列的长度。enumerate()函数用于将一个可遍历的对象组合为一个索引序列，同事列出数据和数据下标，一般用在for循环中。
