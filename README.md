<h1>Sai Tejaswee Vissapragada</h>
<h2>Madrid is my favourite place</h2>
<p>It is the home of <b>Real Madrid FC</b>.</p>
<h3> Directions to my favourite place
<hr>
<ol> <li> Start from Maryville to St.Joseph</li>
     <li>Then St. Joseph to Kansas City</li></ol>
<ul> <li>Drinks </li>
     <li>Snacks</li>
</ul>       </h3>  </hr>  
<hr><h4>Food and Beverages </h4>
<p>Food and Beverages, places where they are available and their cost.</p>
<table>
<tr>
<th> Food/Drink </th>
<th> Location </th>
 <th>Cost</th>
</tr>
<tr>
<td> Milk </td>
<td> Hy-vee </td>
 <td>$1.96  </td>
</tr>
  <tr>
  <td>Pepsi</td>
  <td>Walmart</td>
  <td>$0.96</td></tr>
</table>
</hr>
<a href=https://github.com/TJteja/assignment2-Vissapragada/blob/main/AboutMe.md >AboutMe</a>
<hr><h5>Quotes</h5>
<blockquote><q>If life were predictable it would cease to be life, and be without flavor -<i>Eleanor Roosevelt </i></q><br>
<q>The greatest glory in living lies not in never falling, but in rising every time we fall -<i> Nelson Mandela</i></q>
</blockquote >
</hr>
<hr><h5>Using Bellman-Ford algorithm</h5>
<blockquote><q>Given a graph and a source vertex src in graph, find shortest paths from src to all vertices in the given graph. The graph may contain negative weight edges. 
We have discussed Dijkstra’s algorithm for this problem. Dijkstra’s algorithm is a Greedy algorithm and time complexity is O(V+E LogV) (with the use of Fibonacci heap). Dijkstra doesn’t work for Graphs with negative weight edges, Bellman-Ford works for such graphs. Bellman-Ford is also simpler than Dijkstra and suites well for distributed systems. But time complexity of Bellman-Ford is O(VE), which is more than Dijkstra. 
</q></blockquote>
<a href=https://www.geeksforgeeks.org/bellman-ford-algorithm-dp-23/ >Source link for definition </a><br>

```
struct Edge {
    int a, b, cost;
};

int n, m;
vector<Edge> edges;
const int INF = 1000000000;

void solve()
{
    vector<int> d(n);
    vector<int> p(n, -1);
    int x;
    for (int i = 0; i < n; ++i) {
        x = -1;
        for (Edge e : edges) {
            if (d[e.a] + e.cost < d[e.b]) {
                d[e.b] = d[e.a] + e.cost;
                p[e.b] = e.a;
                x = e.b;
            }
        }
    }

    if (x == -1) {
        cout << "No negative cycle found.";
    } else {
        for (int i = 0; i < n; ++i)
            x = p[x];

        vector<int> cycle;
        for (int v = x;; v = p[v]) {
            cycle.push_back(v);
            if (v == x && cycle.size() > 1)
                break;
        }
        reverse(cycle.begin(), cycle.end());

        cout << "Negative cycle: ";
        for (int v : cycle)
            cout << v << ' ';
        cout << endl;
    }
}
```

<br>
<a href=https://cp-algorithms.com/graph/finding-negative-cycle-in-graph.html >Source link for code </a>



</hr>
 
     
