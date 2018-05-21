# 问题
给定一个二叉树，找出最低部左子的值。
# 代码
```c
int findBottomLeftValue(TreeNode* root)
{
    if (root == NULL) return 0;  

    queue<TreeNode*> qu;
    qu.push(root);
    TreeNode* lastleft = root;  

    while(qu.size() > 0)
    {
            TreeNode* top = qu.front();
            lastleft = top;
            qu.pop();
            if(top->right != NULL) qu.push(top->right);
            if(top->left != NULL) qu.push(top->left);
    }

    return lastleft->val;
}
```
# 总结
编译通过，但是有一点不明白，如果是一棵只有右子树的二叉树，那输出什么？
