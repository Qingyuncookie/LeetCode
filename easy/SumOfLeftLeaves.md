# 问题
求给定二叉树的左子树的和。
# 代码
```python
class Solution(object):
      def sumOfLeftLeaves(self, root):
          ans = 0
          if root:
             l, r = root.left, root.right
             if l and (l.left or l.right) is None:
                ans += l.val
             ans += self.sumOfLeftLeaves(l) + self.sumOfLeftLeaves(r)
          return ans
```
# 总结
如果节点左右子树都不存在，则ans+节点的值，否则，对其左右子树进行递归实现。
