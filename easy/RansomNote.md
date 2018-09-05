# 问题
给定一个勒索信字符串和一个包含所有杂志里字符的字符串，当该信可以被杂志里字符构成时返回true，否则返回false，杂志字符串里每个字符只能使用一次，且均只包含小写。
# 代码
```python
class Solution(object)
      def canConstruct(self, ransomeNote, magazine):
          if len(ransomeNote) > len(magazine)
            return False
          letters = [0] * 26
          for c in magazine:
              letters[ord(c)-97] += 1
          for c in ransomeNote:
              letters[ord(c) - 97] -=1
              if letters[ord(c) - 97] < 0:
                 return False
          return True
 ```
# 总结
字符串的包含问题，若前一个字符串包含于第二个字符串，则返回true，且不考虑顺序。 ord(c)返回字母的ASCII码。小写字母a的ASCII码是97。
