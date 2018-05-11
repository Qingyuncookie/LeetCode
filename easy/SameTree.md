# 问题
给定两个二叉树，判断是否相等。每一个节点都相同。
# 代码
```c
bool isSameTree(TreeNode* p, TreeNode* q)
{  
    if(NULL == p && NULL == q) return true;  
    if(NULL == p || NULL == q || p->val != q->val || !isSameTree(p->left, q->left) || !isSameTree(p->right, q->right) ) return false;  
    return true;      
}
```
# 总结
左子树不相等，右子树不相等，均不成立。
