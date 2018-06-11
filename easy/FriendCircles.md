# 问题
如果矩阵中某一点的值为一，则这一点的横纵坐标值为好朋友，因此会形成一个朋友圈子，找出矩阵中有几个朋友圈子。
# 代码
```c
int findCircleNum(vector<vector<int>>& M)
{
    int n = M.size();
    int num = 0;
    set<int> used;
    while (used.size() < n) {
        stack<int> f;
        for (int i = 0; i < n; i++) {
            if (used.find(i) == used.end()) {
                f.push(i);
                used.insert(i);
                break;
            }
        }
        while (!f.empty()) {
            int index = f.top();
            int i;
            for (i = 0; i < n; i++) {
                if (used.find(i) == used.end() && M[index][i] == 1) {
                    f.push(i);
                    used.insert(i);
                    break;
                }
            }
            if (i == n) {
                f.pop();
            }
        }
        num++;
    }
    return num;
}
```
# 总结
首先，用DFS（深度优先搜索算法）对图中的任意一个未被加入某朋友圈的点进行搜索，将此点先压入栈中，然后查找与此点相连接的点，一旦找到，将此点标记为已入朋友圈，并压入栈中，跳出循环。每次对栈顶的点进行搜索，一旦此点已经搜完其他所有的点方可弹掉。这样直到栈变成空一次，就是找到一个朋友圈。
接下来，继续用DFS搜索未被加入某朋友圈的点，直到所有的点都被标记为加入朋友圈，搜索结束，输出结果。
