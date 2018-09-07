# 问题
给定一个二叉树，重新排列是的最左侧的最后一个数字成为树根节点，按顺序排列，并且所有的节点没有左孩只有右孩。
# 代码
```python
def increasingBST(self, root):
    array = self.inOrder(root)
    if not array:
        return None
    newRoot = TreeNode(array[0])
    curr = newRoot
    for i in range(1, len(array)):
        curr.right =TreeNode(array[i])
        curr = curr.right
    return newRoot

def inOrder(self, root):
    if not root:
        return []
    array = []
    array.extend(self.inOrder(root.left))
    array.append(root.val)
    array.extend(self.inOrder(root.right))
    return array
 ```
# 总结
append() 方法向列表的尾部添加一个新的元素。extend() 方法只接受一个列表作为参数，并将该参数的每个元素都添加到原有的列表中。
