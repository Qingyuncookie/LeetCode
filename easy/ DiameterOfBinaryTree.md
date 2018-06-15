# 问题
给定一个二叉树，求出它的直径。二叉树的直径是二叉树中某两点的最远距离。
# 代码
```c
int diameterOfBinaryTree(TreeNode* root)
{
    int res = 0;
    maxDepth(root, res);
    return res;
}
int maxDepth(TreeNode* node, int& res)
{
    if (!node) return 0;
    int left = maxDepth(node->left, res);
    int right = maxDepth(node->right, res);
    res = max(res, left + right);
    return max(left, right) + 1;
}
```
# 总结
求出所有节点的左右深度之和再加1即是直径。
