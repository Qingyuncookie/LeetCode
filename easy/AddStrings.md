# 问题
给定两个字符串，把它们两个相加，得到它的值，值同样为字符串。
# 代码
```python
class Solution(object):
    def addStrings(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        t1 = 0
        for i in num1:
            t1 *= 10
            t1 += ord(i) - 48


        t2 = 0
        for i in num2:
            t2 *= 10
            t2 += ord(i) - 48

        return str(t1 + t2)
```
# 总结
可以将字符串转换为list，然后逐位相加，生成list，最后将这个list转换为字符串即可。
