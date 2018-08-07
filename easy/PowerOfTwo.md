# 问题
给定一个整数，判断其是否为2的幂次数。
# 代码
```python
class Solution(object):
      def isPowerOfTwo(self, n):
          return n > 0 and not (n & n-1)
```
# 总结
2的幂次n表示成二进制一定是1后面若干个0，n-1一定是一个0后面若干个1，如果n按位与n-1不等于0，则不是2的幂次。这一行代码的意思为n>0，且n&(n-1)=0。
