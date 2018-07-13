# 问题
将二叉树转换为字符串，当只有左孩时右孩不需要加括号，当只有右孩时，左孩需要加括号。
# 代码
```c
string tree2str(TreeNode* t)
{
  if (t==NULL) return "";

  string res;
  res=to_string(t->val);
  if(t->left!=NULL||t->right!=NULL)
  {
    res+="("+tree2str(t->left)+")";
  }
  if(t->right!=NULL)
  {
    res+="(" + tree2str(t->right)+")";
  }
  return res;
}
```
# 总结
左孩右孩的有无一共分为四种情况，其中只有左右孩都不存在的情况下，左孩才不需要加括号，右孩当只有右孩存在时需要加括号。因此分为两种情况讨论。其中，to_string是将整数类型转换为字符串类型。
