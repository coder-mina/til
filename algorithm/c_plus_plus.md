## c++ Grammar

## 공부해야 할 것

* Hash... (unordered_set, unordered_map)

## container

* sequential container: 원소들의 순차적 접근이 가능한 컨테이너
* associative container: 원소들을 key로 접근이 가능한 컨테이너. elements are referenced by their key and not by their absolute position in the container.
* unordered container: organize their elements using hash tables that allow for fast access to elements by their key.

## hash table

* 해쉬 테이블은 많은 자료를 저장하고 있어도 검색이 빠르다. 하지만 저장한 자료가 적을 때에는 메모리 낭비 & 검색 시 오버헤드 발생. 

## unordered_map

* map이란 (key, value)쌍을 저장할 때 사용하는 컨테이너.

* (map models a searchable collection of key-value entries)

* 내부적으로 unordered_map은 key나 value에 대해 소팅이 되어있는 것이 아니고, **해슁해서 버킷으로 저장**하고 있는 것이다. 그래서 map보다 unordered_map이 key로 아이템 접근하는 것은 빠르다! 다만 원소들의 range iteration은 덜 효율적.

* 초기화:

  * ```c++
    unordered_map<char, int> my_map({{'a', 1}, {'b', 2}});
    ```

  * 

* 멤버함수:

  * empty(), size()

  * clear()

  * **average case O(1), worst case linear** in container size

    * (1) operator[]

    * (2) find()

    * ```c++
      auto iter = my_map.find(key);
      if (iter != my_map.end())
      // iter->first, iter->second
      ```

    * (3) insert(): element 1개만 인서트할 때.

      * ```c++
    unordered_map<char, int> my_map;
        my_map.insert(make_pair('a', 1));
        // 만약 이미 존재하는 key를 다시 넣으려고 한다면, 이미 있던 값은 바뀌지 않음!!! 이미 있던 값을 바꾸려면 []사용할 것.
        ```
    
      * 
    
    * (4) erase(): element 1개만 제거할 때
    
      * ```c++
        my_map.erase(key);
        my_map.erase(my_map.find(key));
        ```



## unordered_set

* 내부적으로 원소들은 소팅되어 있는 것이 아니라 해슁되어 버킷으로 정돈되어있다. average case에는 O(1) access가 가능하다. worst case 에는 linear in the size of the container
* 멤버함수: empty(), size(), find(), insert(), erase(), clear()

## ## priority queue

* 디폴트로는 max heap 이다. 원소가 "클수록" 높은 우선순위를 갖는다는 것.

* 만약 이 우선순위를 새롭게 정의하고 싶다면 이런 식으로 하면 된다.

* ```c++
  struct comp {
    bool operator() (int num1, int num2) {
      // num1 이 num2보다 우선순위가 낮으면 true 리턴. 
    }
  };
  priority_queue<int, vector<int>, comp> pq;
  ```

* priority_queue<int> my_pq;

* 멤버함수: empty(), size(), push(), pop(), top()

## stack

- LIFO (last in first out)
- 멤버함수: empty(), size(), push(), pop(), top()

## queue

* FIFO (first in first out)
* 멤버함수: empty(), size(), push(), pop(), front(), back()

## deque (발음은 deck)

* Double-ended queue. 양쪽 끝에서 삽입 삭제 가능: queue + stack

## list

* 멤버함수: empty(), size(), push_back(), push_front(), pop_back(), pop_front(), clear() 
* insert(iterator, value) = iterator 바로 앞에 value 를 인서트
* erase(iterator) = iterator 에 있는 위치의 원소를 제거.

## vector

* 배열 나타낼 땐 웬만하면 vector 쓰자. c-style array 하지 말고...

* vector 뒤에 vector 잇기: 

* 2차원 배열:

  * ```c++
  vector<vector<int> > board(N, vector<int>(N));
    	for (int i = 0; i < N; ++i) {
    		for (int j = 0; j < N; ++j) {
    			board[i][j] = 1;
    		}
    	}
    ```

## C++ 특유의 문법

* static variable: stack 에 할당되는 것이 아니라 static 메모리 영역에 할당되는 것이어서 함수 호출 끝나고도 살아있음.

* template function 

  ```c++
  template <class T>
  T getMax(T a, T b) {
    return (a >= b) ? a : b;
  }
  // when you call this func, 
  int res = getMax<int>(5, 6);
  ```

* **auto** keyword specifies that the type of the variable that is being declared will be automatically deducted from its initializer.

## list manipulation

* list.splice(): 

  * 어떤 리스트 뒤에 다른 리스트 붙일 때 사용.

  * splice 여러 인자 버전이 있는데, 리스트 통으로 옮길 때는 constant 시간 복잡도.

  * ```c++
    list<int> list1 = {1, 2, 3};
    list<int> list2 = {4, 5, 6};
    list1.splice(list1.end(), list2); 
    // list1: {1, 2, 3, 4, 5, 6}
    // list2: (empty)
    ```

  * 

## string manipulation

* c++에서 strings are *objects* that represent sequences of characters.

* string str;

* str.length() == str.size(): returns the number of characters. (same thing)

* operator[] : get character of string

* append() **OR** operator +

  * ```c++
    string str = "hello";
    string str2 = "great";
    str.append(str2);
    // str: "hellogreat", str2: "great"
    ```

  * ```c++
    string s1 = "hello ";
    string s2 = "world";
    cout << s1 + s2 << endl;
    ```

  * 

* replace

* compare() **OR** ==

  * compare():

    * 0 if equal
    * <0 either if the first character that does not match is lower in the compared string, or all compared characters match but the compared string is shorter.
    * '>0' either if the value of the first character that does not match is greater in the compared string or all compared characters match but the compared string is longer.
  * ==
    
  * true **OR** false
    
  * ```c++
    string str1("abb");
    string str2("abc");
    // str1.compare(str2) < 0
    ```
  
* find

  * ```c++
    string str("one needle in a haystack");
    string str2("needle");
    if (size_t found != string::npos) {
      cout << "found" << endl;
    }
    ```
