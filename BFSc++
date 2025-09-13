#include<iostream>
#include<vector>
#include<queue>

using namespace std;

void BFS(int start,const vector<vector<int>>& adj){
    int V = adj.size();

    vector<char> color(V,'W');
    vector<int> d(V, INT_MAX);
    vector<int> pred(V, -1);

    queue<int> Q;

                                //initialize from 
     color[start] = 'G';
    d[start] = 0;
    pred[start] = -1;
    Q.push(start); 

                               // Main BFS Loop
        while(!Q.empty()){
          int u = Q.front();
          Q.pop();
          cout << "Visiting node" << u << endl;

          for(int V: adj[u]){
            if(color[V]  == 'W'){
                color[V] = 'G';
                    d[V] = d[u] + 1;
                 pred[V] = u;
                 Q.push(V);

                 cout << "Discover " << V
                      << "Distance " << d[V]
                      << "pred "     << u << "\n" ;
            }
          }
          color[u] = 'B';
      }

                           //BFS Summary
      cout << "\n Final Result : \n";
          for (int i = 0; i < V; i++){
              cout << " Node " << i
                   << ": Color : " << color[i]
                   << ", Distnce : " << (d[i] == INT_MAX ? -1 : d[i])
                   << ", Pred : " << pred[i] << endl;
          }
}

int main(){

    vector<vector<int>> adj = {
        {1, 2},
        {0, 3},
        {0, 4},
        {1},
        {2}
    };

    BFS(0, adj);
    return 0;
}
