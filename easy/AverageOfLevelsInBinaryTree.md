# 问题
给定一个非空的二叉树，求每一层的平均值。
# 代码
```c
vector<double> averageOfLevels(TreeNode* root)
{
    vector<double>res;
    queue<TreeNode*> q{{root}};           //q此时为二叉树的根值
    while(!q.empty())
    {
        int n=q.size();
        double sum = 0;
        for (int i = 0; i < n; ++i)
        {
            TreeNode* t = q.front(); q.pop();   //记录并弹出队首元素
            sum += t->val;
            if (t->left) q.push(t->left);      //判断上面t是否有左子节点，若有则压入队列
            if (t->right) q.push(t->right);
        }
        res.push_back(sum / n);                //每一次循环，将二叉树的前层弹出，下层压入队列
    }de
    return res;
}
```
# 总结
1.层序遍历：借助队列辅助实现，从左到右，自上而下，依次将二叉树的各节点入队，以此保证输出的顺序是层序排列的。2.queue模板类：需要两个模板参数，一个是元素类型，一个是容器类型。q.push(x):入队，将x接到队列末端。q.pop():弹出队列的第一个元素，不会返回被弹出值。q.front():访问队首元素，即最早被压入队列的元素。q.back():访问队尾元素。q.empty():判断队列空，空时返回true。
