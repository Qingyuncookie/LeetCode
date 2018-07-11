# 问题
给定一个只含0和1二维非空数组,4个直接相连（水平或者垂直）的1可称之为岛，假设四个边界均与海相连。从给定的二维数组中找到面积最大的岛。
# 代码
```c
public:
    int maxAreaOfIsland(vector<vector<int>>& G, int ans=0) {
        for (int i=0,M=(int)G.size(); i<M; ++i){
            for (int j=0,N=(int)G[0].size(); j<N; ++j){
                unordered_set<int> V;
                go(G,M,N,i,j,V);
                ans=max(ans,(int)V.size());
            }
        }
        return ans;
    }
private:
    void go(vector<vector<int>>& G, int M, int N, int i, int j, unordered_set<int>& V) const {
        static vector<pair<int,int>> moves {{0,-1},{-1,0},{0,1},{1,0}};
        if (i<0||j<0||i==M||j==N || G[i][j]==0 || !V.insert(key(i,j,N)).second) return;
        G[i][j]=0;
        for (auto move: moves)
            go(G,M,N,i+move.first,j+move.second,V);

    }
    int key(int i, int j, int N) const { return i*N+j; }
```
# 总结
G[][]二维数组。
