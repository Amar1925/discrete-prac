#include <iostream>
#include <vector>
#include <tuple>

using namespace std;

// Function to calculate in-degrees and out-degrees
tuple<vector<int>, vector<int>> compute_degrees(vector<vector<int>>& graph) {
    int num_vertices = graph.size();
    vector<int> in_degrees(num_vertices, 0);
    vector<int> out_degrees(num_vertices, 0);

    for (int i = 0; i < num_vertices; i++) {
        for (int j = 0; j < num_vertices; j++) {
            if (graph[i][j] == 1) {
                out_degrees[i]++; // Incrementing out-degree
                in_degrees[j]++; // Incrementing in-degree
            }
        }
    }

    return make_tuple(in_degrees, out_degrees); // Returning the values as a tuple
}

int main() {
    // Our graph represented as an adjacency matrix
    vector<vector<int>> G = {{0, 1, 1, 0},
                             {0, 1, 1, 1},
                             {1, 0, 0, 1},
                             {1, 1, 1, 0}};

    vector<int> in_degrees, out_degrees;
    tie(in_degrees, out_degrees) = compute_degrees(G);

    cout << "Vertex\tIn-degree\tOut-degree" << endl;
    for (int i = 0; i < G.size(); i++) {
        cout << i << "\t" << in_degrees[i] << "\t\t" << out_degrees[i] << endl;
    }

    return 0;
}
