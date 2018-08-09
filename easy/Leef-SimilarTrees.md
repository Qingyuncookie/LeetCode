# 问题
给定两个二叉树，判断是否为叶相似二叉树。叶值为二叉树每个分叉的最后一个树叶按从左向右的顺序排列。
# 代码
```python
class Solution:
  def findLeaf(self, n, node):
      if node.right:
        self.findLeaf(n, node.left)   
      if node.right:
        self.findLeaf(n, node.right)
      if not node.left and not node.right:
        self.leafs[n].append(node.val)
        return
      else:
        return
def leafSimilar(self, root1, root2):
    self.leafs = [[],[]]
    self.findLeaf(0,root1)
    self.findLeaf(1,root2)
    return self.leafs[0] == self.leafs[1]

```

# 总结
利用函数的迭代，当一个树叶没有子树叶时入栈保存。函数迭代完之后回到迭代之前的地方继续往下执行。分成两个函数，先分别计算两个二叉树的叶值再进行比较。
