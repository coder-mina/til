# Map

## hash table

* bucket array
* hash function:
  * hash function f maps keys of a given type to integers in a fixed interval [0, N-1]
  * hash function h(x) = h2(h1(x)) where h1 is hash code, h2 is compression function
* collision handling
  * separate chaining (각 버킷마다 linked list 달기)
  * open addressing: (colliding item is placed in a different bucket)
    * linear probing: colldiing item을 다음으로 빈 버킷에 넣기.
* load factor & re-hashing (moving to larger hash table to keep load factor small)
* worst case occurs when all the keys inserted into MAP collide.
* But when well designed the expected running time of all MAP operations in a hash table is O(1).
* In practice, hashing is very fast provided the load factor is not close to 100%

## skip list

* we use **randomized** algorithm to insert items into a skip list.
* 