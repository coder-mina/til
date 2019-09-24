## Heap-Sort

* in-place heap sort: 
  * https://www.ideserve.co.in/learn/heap-sort
  * **algorithm/heap_sort.cpp**
  * bottom-up heap construction은 O(n) 시간. (this is faster than n successive insertions and speeds up the first phase of heap-sort) bottom-up heap construction이란 n개의 원소들을 가지고 heap을 만들 때, "밑에서부터" heapify해나가는 방식이다. 두 개의 힙을 합칠 때, heap-order property를 회복하기 위해 루트를 downheap만 하면 되는 것! 
  * 한 번의 heapify 에는 O(logN) 시간 소요.
  * in-place heap sort는 총 O(NlogN) 시간

## Quick-Sort

* randomized sorting algorithm
* Divide and conquer paradigm
* **algorithm/quick_sort.cpp**
* worst case TC = O(n^2) (when the pivot is the unique max or min element -> then, one of L and G has size n-1 and the other has the size 0: so total running time is n + (n-1) + ...+ 1)
* expected running time: O(NlogN)

* in-place quick sort: pivot 뽑고, left (pivot보다 작다)-> , <-right (피봇보다 크다) 하다가, left >= pivot, right<=pivot이면 swap. ... left<=right일 동안 반복. 그 이후 left가 가리키는 곳과 pivot을 swap (요건 pivot이 배열의 마지막 원소 자리에 있어서 가능한 듯하기도.)

## Merge-Sort

* O(NlogN) 

## Radix-Sort

* Bucket-sort: 
  * n개의 아이템들을 소팅할 때, 아이템들이 [0, N-1]에 있다는 것을 알면 O(n+N) 시간복잡도
  * stable sort property를 가짐 (=relative order of any two items with the same key is preserved after the execution of the algorithm)
* Lexicographic-sort:
  * d-tuple들 N개를 사전 오더로 정렬하는 것. LSB부터 MSB순으로 각 비트별로 **stableSort()**를 하는 것! (워킹하는 이유 = LSB순으로 소팅을 한 다음 점점 중요한 비트에 대해 소팅을 하므로, 중요한 비트가 최종적인 우선순위가 있게 소팅이 될 수가 있는 것이다. 또한 stableSort를 하므로 순서가 어그러지는 일 발생 안 함!)
  * d-tuple들 N개를 소팅하는 데에 걸리는 시간 = O(d * T(N)) where T(N) = running time of stable sort per bit
* Radix-sort:
  * **specialization** of lexicographic-sort that uses "bucket sort" as the **stable sorting** algorithm in each dimension.
  * **각 dim i에 있는 키들이 [0, N-1] 범위 내의 정수라는 것을 알 때 적용 가능**한 소팅방법.
  * d-tuple들 n개를 (숫자들은 [0, N-1]범위내) 소팅하는 데에 걸리는 시간 = O(d * (n+N)) 

## Selection-Sort

* O(n^2)

## Insertion-Sort

* O(n^2)

 