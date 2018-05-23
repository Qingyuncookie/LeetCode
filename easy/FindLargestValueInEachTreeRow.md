# 问题
# 代码
```c
vector<int> largestValues(TreeNode* root)
{
  int c=0,n=0;
  vector<int> res;
  if(root==NULL)
  {
    return res;
  }
  queue<TreeNode*> q;
  q.push(root);
  c=1;
  while(!q.empty())
  {
    int Max=0;
    while(c!=0)
    {
      TreeNode* t=q.front();
      q.pop();
      Max=max(Max,t->val);
      if (t->left!=NULL)
      {
        q.push(t->left);
        n++;
      }
      if(t->right!=NULL)
      {
        q.push(t->right);
        n++;
      }
      c--;
    }
    res.push_back(Max);
    c=n;
    n=0;
  }
  return res;  
}
```
vector<int> res;
queue<TreeNode*> qu;
qu.push(root);
int n=qu.size();
while(n>0)
{
    sort(qu.begin(),qu.end());
    res.push_back(qu[n]);
    qu.pop
}
return res;
# 总结
