# Tree

## 공부해야 할 것들
* cracking 4.8 마지막 optimized 는 이해 안 함.
* cracking 4.9 BST sequences 직접 코딩 짜볼 것 (이해는 함.)
* 숫자들 주어졌을 때 이것으로 만들 수 있는 BST 개수 세어 보기.... 흐음...!!!
* cracking 4.10: 
  * 문제 정의에 따르면, T2가 T1의 subtree라는 것은, T2 루트가 n일 때 n에서의 T1 트리랑 완전히 똑같을 때라는 것이다. 그런데, 풀이에 있듯이 T2의 pre order string 이 T1의 pre order string 인지 아닌지를 보면, 그 밑에 더 많은 노드가 달려있어도 subtree 라고 판단하는 일이 발생할 수도 있다. 아아 그래서 null node 도 place holder 로 넣는 것이구나.
  * simple approach의 TC가 O(n+m)이라고 되어있는데, substring인지 체크하는 부분이 O(n*m) 걸릴 수도 있다..C++은 string::find()의 TC가 unspecified 되어 있다...
* 
## 면접 때 제한 조건으로 물어볼 만한 것들
* binary tree 를 linked list 구조로 구현할 때, parent 에 대한 링크가 있는 노드 구조라고 가정해도 되나요?
* 두 노드의 common ancestor 를 찾는 함수를 짜는 것이 문제인데, 이 함수의 인풋으로 들어오는 두 노드는 항상 같은 트리 내에 있다고 가정해도 되나요?
* BST 나 heap을 만들 때, 노드들의 value는 모두 distinct 하다고 가정할 수 있나요?
* "It all depends on what assumptions you make and whether you prioritize reducing the average case runtime at the expense of the worst case runtime. This is an excellent point to make to your interviewer." (cracking)

## Tree Concepts

* **complete binary tree** = binary tree in which every level of the tree is fully filled, except for perhaps the last level. To the extent that the last level is filled it is filled left to right.
* full binary tree (proper binary tree) = binary tree in which every node has either 0 or 2 children.
* perfect binary tree = full && complete

## Binary search tree

* 정의: for every node in the tree, nodes on the left < node < nodes on the right  즉, 모든 노드에 대해 노드 왼쪽의 최댓값 < 노드 < 노드 오른쪽의 최솟값.
* what if the tree has nodes with duplicate values?
  * all nodes on the left <= node < all nodes on the right 으로 정의를 하자.
  * 그래야, searching을 할 때, 왼쪽/오른쪽 중 어느 쪽으로 내려가야 하는지 알 수 있다.
## heap

* 정의: heap is a binary tree with heap order property and complete binary tree property!
  * min-heap: for every node in the tree, node > parent (min value at the root)
  * max-heap: for every node in the tree, node < parent (max value at the root)
*  implementation: 보통은 array 구조로 구현한다. 
*  priority queue는 보통 heap으로 구현!