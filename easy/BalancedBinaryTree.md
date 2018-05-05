# 问题
给定一棵二叉树，检测其高度上是否平衡。
# 代码
```c
bool isBalanced(TreeNode* root) {  
    if (!root) return true;  
    if(abs(height(root->left)-height(root->right))>1) return false;  
    return isBalanced(root->left) && isBalanced(root->right);   
}  

int height(TreeNode* node){  
    if(!node) return 0;  
    return max(height(node->left),height(node->right))+1;  
}
```
# 总结
一棵高度上平衡的二叉树被定义为一棵每个节点上的两个子树上的深度差不能大于1的二叉树。
