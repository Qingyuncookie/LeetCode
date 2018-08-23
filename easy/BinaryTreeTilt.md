# 问题
给定一个二叉树，返回这个二叉树的总倾斜。节点的所有左子树的和和所有右子树的和的差值称为倾斜度，总倾斜度为二叉树所有倾斜度的和。
# 代码
```python
def findTilt(self, root):
  self.ans = 0
  def _sum(node):
    if not node: return 0
    left, right = _sum(node.left), _sum(node.right)
    self.ans += abs(left - right)
    return node.val + left + right
  _sum(root)
  return self.ans
```
# 总结
注意Python可以两个变量一起赋值。定义一个sum来计算
