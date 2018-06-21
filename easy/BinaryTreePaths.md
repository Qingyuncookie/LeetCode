# 问题
给定一个二叉树，给出所有根到叶的路径。叶：没有子孩。
# 代码
```c
vector<string> binaryTreePaths(TreeNode* root)
{
    vector<string>ans;
    string item;
    dfs(root, item, ans);
    return ans;
}

void dfs(TreeNode* root, string& item, vector<string>& ans )
{
    if(!root)  return;
    string before=item;
    item+=to_string(root->val)+"->";
    if(!root->left&&!root->right)
    {
        item.erase(item.end()-2,item.end());          
        ans.push_back(item);
    }
    dfs(root->left, item, ans);
    dfs(root->right, item, ans);
    item=before;
}
```
# 总结
自定义一个dfs函数。
