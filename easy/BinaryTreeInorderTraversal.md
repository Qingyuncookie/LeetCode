# 问题
给定一个二叉树，返回其中序遍历节点的值。
# 代码
```c
//递归算法
vector<int> v;
vector<int> inorderTraversal(TreeNode* root)
{
  if (root != NULL)
  {
    inorderTraversal(root->left);
    v.push_back(root->val);
    inorderTraversal(root->right);
  }
  return v;
}

//迭代算法
vector<int> inorderTraversal(TreeNode* root) {
    vector<int> result;
    stack<TreeNode*> tempStack;
    while (!tempStack.empty() || root != NULL) {
        if (root != NULL) {
            tempStack.push(root);
            root = root->left;
        }
        else {
            root = tempStack.top();
            result.push_back((tempStack.top())->val);
            tempStack.pop();
            root = root->right;
        }
    }
    return result;
}

```
# 总结
先序：考察到一个节点后，即刻输出该节点的值，并继续遍历其左右子树。(根左右)。
中序：考察到一个节点后，将其暂存，遍历完左子树后，再输出该节点的值，然后遍历右子树。(左根右)。
后序：考察到一个节点后，将其暂存，遍历完左右子树后，再输出该节点的值。(左右根)。
