# 问题
给定一个配对好的字符串，确定字符串的得分。
# 代码
```python
def scoreOfParentheses(self,S):
    depth = 1
    ans = 0
    add = True
    for ch in S:
        if ch == "(":
            depth = depth*2
            add = True
        elif ch == ")":
             depth = depth/2
              if add == True:
                  ans += depth
                  add = False
return ans    
```
# 总结
()得一分，(())嵌套翻倍得分。
遇到“（”深度增加，分数翻倍，遇到 “）”，深度减小，由翻倍变为除2，加上原来的所得分数。切只有再次遇到”（”才能继续加，遇不到则ans即结果保持不变。上括号决定总体个数，下括号决定嵌套位置。
