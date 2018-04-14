# 问题
合并二叉树
# 代码
```C
TreeNode* mergeTrees(TreeNode* t1, TreeNode* t2)
{
    if (!t1) return t2;
    if (!t2) return t1;
    TreeNode* t=new TreeNode(t1->val + t2->val);
    //递归函数
    t->left=mergeTrees(t1->left,t2->left);
    t->right=mergeTrees(t1->right,t2->right);
    return t;
}
```
# 总结
1.二叉树是每个节点最多只有两个分支的树结构，分支通常被称为左子树和右子树。二叉树的深度是从根节点到叶节点依次经过的节点形成树的一条路径其最长路径的长度。
2.DFS（Depth-First-Search)：深度优先搜索算法，是一种用于遍历或搜索树或图的算法。沿着树深度遍历树的节点，尽可能深的搜索树的分支。（盲目搜索）
3.合并规则：都存在的节点，就将节点值加起来，否则空的位置就由另一个树的节点来代替。
4.递归函数：其中每一步都要用到前一步或前几步的结果。
