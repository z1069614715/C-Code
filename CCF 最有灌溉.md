# C-Code
C++ 代码

[最优灌溉](http://118.190.20.162/view.page?gpid=T18)

# 典型最小生成树

    //
    // Created by Admin on 2019/3/12.
    //最优灌溉

    using namespace std;

    #include <iostream>
    #include <queue>
    #include <vector>
    #include <string.h>

    #define MAXN 1005

    struct Edge {
        int next, cost;

        bool operator<(const Edge &a) const {
            return cost > a.cost;
        }
    };

    int n, m, vis[MAXN];
    vector<Edge> map[MAXN];

    int prim() {
        int res = 0;
        int Edgecount = n - 1;
        memset(vis, 0, sizeof(vis));
        priority_queue<Edge> q;
        for (int i = 0; i < map[1].size(); ++i) {
            q.push(map[1][i]);
        }
        vis[1] = 1;
        while (!q.empty() && Edgecount != 0){
            Edge a = q.top(); q.pop();
            if (vis[a.next]) continue;
            --Edgecount;
            vis[a.next] = 1;
            res += a.cost;
            for (int i = 0; i < map[a.next].size(); ++i) {
                if (!vis[map[a.next][i].next]){
                    q.push(map[a.next][i]);
                }
            }
        }
        return res;
    }

    int main() {
        cin >> n >> m;
        for (int i = 0; i < m; ++i) {
            int a, b, cost;
            cin >> a >> b >> cost;
            map[a].push_back(Edge{b, cost});
            map[b].push_back(Edge{a, cost});
        }
        cout << prim();
        return 0;
    }
