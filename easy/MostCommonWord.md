# 问题
给定一段文字，和一串禁止词，找出除禁止词外在段落中出现次数最多的词。
# 代码
```python
class Solution:
      def mostCommonWord(self, paragraph, banned):
          p = re.compile(r"[!?',;.]")
          sub_para = p.sub('', paragraph.lower())
          words = sub_para.split(' ')
          words = [word for word in words if word not in banned]
          count = collections.Counter(words)
          return count.most_common(1)[0][0]
```
# 总结
re模块中包含一个重要函数是compile(pattern [, flags]) ，该函数根据包含的正则表达式的字符串创建模式对象。
正则化的使用！！！
