# 问题
给定一个二叉树，计算其最大深度。
# 代码
```c
int maxDepth(Treenode* root)
{
  if(Null==root)
  return 0;

  int depth_l = maxDepth(root->left);
  int depth_r = maxDepth(root->right);

  return depth_l > depth_r ? depth_l + 1:depth_r + 1
}
```
# 总结
最大深度是指从根节点到最远叶节点之间的节点数目，最远叶节点不再有分支。
a>b?a:b，意为如果a>b，则返回a，否则返回b.
