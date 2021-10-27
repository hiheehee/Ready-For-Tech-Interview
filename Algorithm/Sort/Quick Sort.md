# Quick Sort
<img width="80%" src="http://www-scf.usc.edu/~zhan468/public/Notes/resources/C411339B79F92499DCB7B5F304C826F4.gif"/>  

* 분할 정복(Divide and Conquer)을 통해 정렬하는 알고리즘
* pivot을 기준으로 정렬 -> 쪼갬 
* 불안정 정렬(Unstable Sort)
* java의 Arrays.sort() <= 내부적으로 Dual Pivot Quick Sort로 구현
* 시간 복잡도 : 최악 O(n^2), 평균 & 최선 : Θ(nlogn)
* 공간 복잡도 : O(N)
* 방법
  1. 기준이 될 pivot 정함 <= 선정 방식 : 첫번째, 중간, 마지막, 랜덤
  2. pivot을 기준으로 pivot보다 작으면 왼쪽, pivot보다 크면 오른쪽으로 나눔 => Divide
  3. 정렬이 될때까지 1-2번 반복 수행 => Conquer

```java

```
