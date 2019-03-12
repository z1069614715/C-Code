# C-Code
C++ 代码

[数据中心](http://118.190.20.162/view.page?gpid=T83)

# _C++ Prim_

    //
    // Created by Admin on 2019/3/12.
    //
    using namespace std;

    #include <iostream>
    #include <algorithm>
    #include <queue>
    #include <vector>
    #include <string.h>

    #define MAXN 500100

    struct Edge {
        int next, cost;
        //建立小顶堆
        bool operator<(const Edge &a) const {
            return cost > a.cost;
        }
    };

    int n, m, root;
    int vis[MAXN];
    vector<int> res;
    vector<Edge> vec[MAXN];

    int prim() {
        int Edgecount = n - 1;//遍历顶点数量
        priority_queue <Edge> q;//优先队列
        for (int i = 0; i < vec[root].size(); ++i) {
            q.push(vec[root][i]);
        }
        memset(vis, 0, sizeof(vis));
        vis[root] = 1;
        while (!q.empty() && Edgecount != 0) {
            Edge a = q.top(); q.pop();//取出最小顶点，且弹出
            if (vis[a.next]) continue;//如果访问过就拜拜
            //没有访问过就加进去
            res.push_back(a.cost);
            Edgecount--;
            vis[a.next] = 1;
            for (int i = 0; i < vec[a.next].size(); ++i) {
                if (!vis[vec[a.next][i].next]) q.push(vec[a.next][i]);//添加的原因，如果这条边没有访问过，都需要加，因为要取得这条边的最小权值
            }
        }
        sort(res.begin(),res.end());
        cout << res[res.size() - 1];
    }

    int main() {
        cin >> n >> m >> root;
        for (int i = 0; i < m; ++i) {
            int a, b, cost;
            cin >> a >> b >> cost;
            vec[a].push_back(Edge{b, cost});
            vec[b].push_back(Edge{a, cost});
        }
        prim();
        return 0;
    }
    
# _C++ Kruskal_

    //
    // Created by Admin on 2019/3/12.
    //
    using namespace std;

    #include <iostream>
    #include <algorithm>
    #include <vector>

    #define MAXN 500100

    struct node {
        int a, b, cost;
        bool operator<(const node &a)const{
            return cost < a.cost;
        }
    } map[MAXN];

    int n, m, root;
    int pre[MAXN];
    vector<int> vec;

    int findfa(int a) {
        int b = a;
        while (b != pre[b]) {
            b = pre[b];
        }
        //路径压缩
        while (a != b){
            int i = pre[a];
            pre[a] = b;
            a = i;
        }
        return b;
    }

    int Kruskal() {
        //记得初始化父节点
        for (int i = 1; i <= n; ++i) {
            pre[i] = i;
        }
        for (int i = 0; i < m; ++i) {
            int a = findfa(map[i].a);
            int b = findfa(map[i].b);
            if (a != b){
                pre[a] = b;
                vec.push_back(map[i].cost);
            }
            if (vec.size() == n - 1){
                return vec[vec.size() - 1];
            }
        }
    }

    int main() {
        cin >> n >> m >> root;
        for (int i = 0; i < m; ++i) {
            cin >> map[i].a >> map[i].b >> map[i].cost;
        }
        sort(map,map + m);
        cout << Kruskal();
        return 0;
    }
