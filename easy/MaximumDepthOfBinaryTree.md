# 问题
给定一个二叉树，计算其最大深度。
# 代码
```c
int maxDepth(Treenode* root)
{
  if(Null==root)
  return 0;

  int depth_1 = maxDepth(root->left);
  int depth_r = maxDepth(root->right);

  return depth_1 > depth_r ? depth_1 + 1:depth_r + 1
}
```
# 总结
最大深度是指从根节点到最远叶节点之间的节点数目，最远叶节点不再有分支。
