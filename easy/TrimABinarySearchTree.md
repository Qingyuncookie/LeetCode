# 问题
给定一个边界[L,R]，修剪一棵二叉搜索树。
# 代码
```C
TreeNode* trimBST(TreeNode* root, int L, int R)
{
    if(!root) return NULL;
    if(root->val<L) return trimBST(root->right,L,R);
    if(root->val>R) return trimBST(root->left,L,R);
    root->left=trimBST(root->left,L,R);
    root->right=trimBST(root->right,L,R);
    return root;

}
```
# 总结
1.二叉搜索树的性质：左<根<右，修剪后的二叉树也应该符合这个性质。当根植因为小于L被修剪后，返回右子节点，当根植因为大于R被修剪后，返回左子节点。2.递归实现。
