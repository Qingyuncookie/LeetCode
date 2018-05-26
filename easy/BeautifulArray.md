# 问题
给定N个整数，问优美排列的个数。优美排列：数字可以整除下标或下标可以整除数字。
# 代码
```c
int countArrangement(int N)
{
   int res = 0;
   vector<int> visited(N + 1, 0);
   helper(N, visited, 1, res);
   return res;
}
void helper(int N, vector<int>& visited, int pos, int& res) {
   if (pos > N) {
       ++res;
       return;
   }
   for (int i = 1; i <= N; ++i) {
       if (visited[i] == 0 && (i % pos == 0 || pos % i == 0)) {
           visited[i] = 1;
           helper(N, visited, pos + 1, res);
           visited[i] = 0;
       }
   }
}
```
# 总结
helper：组合空间。
