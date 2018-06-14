# 问题
给定一个排好顺序的数组，将其转变为一个平衡二叉搜索树。一个高度平衡的二叉树被定义为一个二叉树中每个节点的两个子树的深度相差不会超过1。
# 代码
```c
TreeNode* sortedArrayToBST(vector<int>& nums)
{
    return dfsBSTree(nums,0,nums.size()-1);
}
TreeNode* dfsBSTree(vector<int>& nums, int start,int end)
{
    if(start>end) return NULL;
    int medium = (start+end)/2;//取整
    TreeNode* root = new TreeNode(nums[medium]);
    if(start==end) return root;
    root->left = dfsBSTree(nums,start,medium-1);//找左子树
    root->right = dfsBSTree(nums,medium+1,end);//找右子树
    return root;
}
```
# 总结
采用递归实现，寻找左右子树，保证高度差不超过1。
