# 问题
求一棵树的所有子树的元素和找到出现次数最多的和的值。
# 代码
```c
unordered_map<int, int> um;
int sum = 0, max = 0;
int SubtreeSum(TreeNode* root)
{
    if(root == NULL)return 0;
    if(root->left == NULL and root->right == NULL)
    {
      sum = root->val;
      um[sum] += 1;
      max = max > um[sum]?max:um[sum];
      return sum;
    }
    else
    {
        sum = root->val + SubtreeSum(root->right) + SubtreeSum(root->left);
        um[sum] += 1;
        max = max > um[sum]?max:um[sum];
        return sum;
    }

}
vector<int> findFrequentTreeSum(TreeNode* root)
{
     vector<int> res;
     SubtreeSum(root);
       //cout << max << endl;
     unordered_map<int, int>::iterator it = um.begin();
     for(; it != um.end(); it ++)
     {
        if(it->second == max) res.push_back(it->first);
     }
     return res;
}
```
# 总结
unordered_map的使用。
