# Array
* 논리적 저장 순서와 물리적 저장 순서가 일치하는 자료구조
* 메모리 공간에 할당할 사이즈를 미리 지정해 사용하는 자료구조 => immutable
* 인덱스를 이용해 원소에 접근 가능 => O(1)
* 삭제 & 삽입시 shfit 진행 해야 함 => O(N)

# Dynamic Array
* Java => ArrayList, C++ => Vector
* 논리적 저장 순서와 물리적 저장 순서가 일치하는 자료구조
* 메모리 공간에 할당할 사이즈를 미리 지정하지 않고 사용하는 자료구조
* 인덱스를 이용해 원소에 접근 가능 => O(1)
* 삭제 & 삽입시 shfit 진행 해야 함 => O(N)

# LinkedList
* 논리적 저장 순서와 물리적 저장 순서가 다른 자료구조
* 한 노드에 연결될 노드의 포인터 위치를 가리키는 방식
* 메모리 공간에 할당할 사이즈를 미리 지정하지 않고 사용하는 자료구조
* 검색, 삭제, 삽입 모두 O(N) But 삽입 & 삭제 모두 Array 보다 빠름
