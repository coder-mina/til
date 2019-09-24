# Graph

## Things to study
* 

## 그래프 용어

* endpoints of an edge
* edges incident on a vertex
* adjacent vertices

## Representing Graph ADT

* (1) adjaceny list

  ```c++
  list<int> * adj = new list<int>[V];
  ```

* (2) array of edges

* (3) adjacency matrix

  * ```c++
    int graph[3][3] = {{1, 2, 3},
                       {2, 3, 4},
                       {4, 5, 6}};
    ```

  * 

## Dijkstra's shortest path

* 시간복잡도: O((N+M)logN) (vertex 개수 = N, edge 개수 = M일 때) 
* Greedy algorithm의 일종이다.
* "weighted" breadth-first search starting at some vertex v.
* 가정: connected / undirected / nonnegative edge weights
* [방법] 
  - 그래프는 adjaceny list로 나타낸다.
  - A 노드에서 그래프의 다른 노드들에 이르는 최단거리를 몽땅 구하고자 한다.
  - 그래프의 모든 노드들에 대해 (dist label, node)를 설정하여 PQ에 넣는다. 이때 A 의 레이블 = 0, 나머지 노드들은 무한대로 설정. 
  - 레이블 = 이 노드에 이르기 위해 현재까지 알려진 A에서부터의 최단 거리
  - PQ가 empty가 될 때까지 하나씩 뽑으면서: PQ에서 나온 노드 B의 인접 노드들 (예컨대 z)의 레이블을 업데이트해줄 것!  z의 label = min(z의 label, B의 레이블 + B로부터의 edge의 weight)

* Property:
  * subpath of shortest path is itself a shortest path. (A-...>B...->C가 A->C 최단거리라면, A...->B 도 최단거리이다. 만약 이게 최단거리가 아니라면 A에서 B로 가는 더 짧은 경로가 있다는 것이 되니까.)
  * there is a tree of shortest paths from a start vertext to all the other vertices.

* edge relaxation = is trying to lower the cost of getting to a vertex by using another vertex. (처음에는 최단거리를 무한으로 overestimate -  스프링을 팽팽하게 당기고 이;ㅆ다가 점점 릴렉스되어 탠션이 줄어드는 것)
* does it work on non-negative weight edge?

## Minimum Spanning Tree

* spanning tree = tree인 spanning subgraph (= 그래프의 모든 vertices 포함한다는 것)  (가중치가 있는 연결된 무향 그래프의 모든 꼭짓점을 포함하면서 엣지들의 가중치의 합이 최소가 되는 부분 그래프인 트리.)

* **undirected graph**에서!!!

* ### (1) Kruskal

  * [방법]
    * 그래프는 edge list 로 나타낸다.
    * 그래프는 edge들을 오름차순 정렬하여 순차적으로 보면서 (PQ에 엣지들을 몽땅 넣어두고 하나씩 꺼내거나 아님 소팅 알고리즘을 써서 엣지 리스트를 정렬하거나) 
    * cycle을 이루지 않는 edge들만 MST로 추가해넣는다! (cycle 여부 판단은 union find 알고리즘 사용) 
    * vertices개수가 N개인 그래프라면 이것을 반복하다가 (N-1)개의 edge가 모이면 STOP!
  * 시간복잡도:  O(ElogE + ElogV) 
    * (설명 = 엣지 소팅하는 데에 ElogE, 모든 엣지 순회하면서(E) find, union하게 되는데 find, union은 logV, 따라서 )

* ### (2) Prim

  - MST에 이미 포함된 노드들 - 아직 포함 안 된 노드들을 연결하는 min weight edge를 선택한다!
  - [방법]
    - 그래프는 adjaceny list로 나타낸다.
    - A 노드를 출발점으로 뽑는다.
    - 그래프의 모든 노드들에 대해 (dist label, node)를 설정하여 PQ에 넣는다. 이때 A 의 레이블 = 0, 나머지 노드들은 무한대로 설정. 
    - 레이블 = 현재까지 형성된 클라우드에서의 최단 거리
    - PQ가 empty가 될 때까지 하나씩 뽑으면서 MST에 추가: PQ에서 나온 노드 B의 인접 노드들의 레이블을 업데이트해줄 것!  label = min(label, B로부터의 edge의 weight)
    - 다익스트라랑 거의 비슷! 다만 label의 정의만 다를 뿐.
  - 시간복잡도: O((V+E)logV)

* does it work on negative weight edge?

  

## backtracking

* N-queens problem (https://www.geeksforgeeks.org/printing-solutions-n-queen-problem/)
* code: algorithm/n_queen.cpp

## disjoint-set data structure & union-find algorithm

* 서로소인 여러 개의 집합들이 있을 때, 원소가 그 중 어떤 집합에 속하는지를 찾는 find()와 두 집합을 하나의 집합으로 합칠 때 사용하는 union() 연산을 수행하는 데에 사용하는 데이터 구조이다. 처리를 할 때 사용되는 알고리즘이다. union(), find()
* undirected graph에서 사이클이 존재하는지 여부 따질 때 사용.
* (0) naive implemention: 트리 구조를 이용하여 서로소 집합들을 표현하는데, 특정 집합에 속한 원소들은, 모두 같은 트리에 있는 것이다. union(), find()는 각각 O(n) 소요. 
* (1) union by rank: improvement of union(), 짧은 트리를 깊은 트리 밑에 붙이는 방법.
* (2) path compression: improvement of find(), 노드의 루트를 찾으면, 그 노드의 parent를 루트로 업데이트. 나중에 똑같은 find()를 할 때 트리를 다시 또 루트까지 탐색하지 않아도 되도록.
* (1), (2)를 모두 한꺼번에 이용하면 union(), find() 가 각각 O(logn)보다 짧은 시간에 가능해지고, amortized TS는 거의 constant 가 된다고 함. (증명은 찾지 못했고, 이해 못 함.)

## Number of connected components

* DFS 를 사용해서 카운트 가능.
* undirected graph라면 union-find 사용해서 카운트 가능.

## Topological Sort

* [정의] directed acyclic graph (DAG) 에 대해, 모든 directed edge (u, v) 에 대해 u가 v보다 앞에 오도록 하는 vertices 의 linear ordering 을 topological sorting 이라고 함. 
* 이런 소팅은, DAG 에 대해서만 가능. 즉, directed graph에서 사이클이 존재하면 이런 소팅이 **불가능** 
* [구현]
* (1) incoming edge 개수 0 인 노드들은, order_array 에 넣어도 된다는 사실을 이용: 노드마다 incoming edge 개수 정보를 들고 있고, 처음에 adjaceny list 로 그래프 구조를 나타낸 뒤, incoming edge 개수 0인 노드들을 order_array에 넣는다. order_array를 노드 개수 만큼 다 채울 때까지 순회하면서, 그 노드의 자식 노드들의 incoming edge 개수를 --시키고, 그 값이 0이 되면 order_array에 넣어준다. order_array가 다 차지 않았는데, 더이상 처리할 노드가 없다면 사이클이 존재하는 것이므로 그때 에러 리턴.
* (2) DFS의 변형: deque 를 하나 만들고 계속 "앞에다가" 노드를 푸시해넣자. (최종 답은 deque를 앞에서부터 읽으면 ordering 답이 됨.)
* u->v->w 라면, v, w가 deque에 다 들어간 뒤에야 u를 넣을 수 있다. 즉, DFS 를 통해 이웃 노드들을 다 순회했다면 본인을 deque에 넣으면 된다. 이때 cycle detection을 하기 위해 노드 state 를 정의한다. enum State {BLANK, IN_PROCESS, DONE}; 
* BLANK 은 방문 안 한 것, IN_PROCESS는, 본인 노드의 이웃들을 보는 게 안 끝나서 아직 deque 에 안 들어간 상황, DONE은 본인 노드가 deque 에 들어간 상황. IN_PROCESS 인 노드를 만난다면, 사이클 존재하는 것! (그림 그려보면 쉽게 이해 가능.)