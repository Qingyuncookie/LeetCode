# 问题
给定一个二叉搜索树，将所有的节点替换为不小于其本身的各节点的和。
# 代码
```python
class Solution(object):    # 创建一个类，object类是所有类都会继承的类。
    def convertBST(self, root):   #创建一个对象convertBST，其中self与root是其属性，self表示创建的类实例本身，在传入参数时不要要传入self参数，Python解释器会自己将实例变量传进去。且在勒种定义函数时，第一参数永远是类的本身实例变量self，且调用时无需传递该参数。
        self.cur_sum = 0
        self.convertHelper(root)
        return root
    def convertHelper(self, root):
        if not root:
            return
        self.convertHelper(root.right)
        root.val+=self.cur_sum
        self.cur_sum = root.val
        self.convertHelper(root.left)
```
# 总结
面向对象最重要的就是类与实例，类是抽象的模板，而实例是根据类创建出来的对象.
