# 问题
反转二叉树。即每一个节点的左右子树对换，左右子树的左右节点也交换。
# 代码
```c
TreeNode* invertTree(TreeNode* root)
{
    TreeNode* tmp;
    if(!root)  return NULL;
    if(root->left) root->left=invertTree(root->left);
    if(root->right) root->right=invertTree(root->right);
    tmp=root->right;
    root->right=root->left;
    root->left=tmp;
    return root;
}
```
# 总结
递归实现。
