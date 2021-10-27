# Bubble Sort
<img width="80%" src="https://cdn-images-1.medium.com/max/1600/1*ZQmdM7My9QIhvxj98hrweg.gif"/>  

* 서로 인접한 원소의 대소관계를 비교하여 정렬하는 알고리즘
* 선택 정렬 (Selection Sort)과 유사
* 제자리 정렬 : in-place sorting <= 다른 메모리 공간 필요하지 X
* 시간 복잡도 O(N^2) <= 최악, 최선, 평균 모두
* 공간 복잡도 O(N)
* 방법
  1. 0번째 <=> 1번째, 1번째 <=> 2번째, 2번째 <=> 3번째, 3번째 <=> 4번째, ... 차례로 비교하며 순서 바꾸기 
  2. n개의 수 중에서 1번째 회전이 끝나면 맨 뒤에 가장 큰 수가 자리하기 때문에 다음에는 n-2개만 비교하면 됨, ... => i번째 회전시 n-i-1회전만 진행하면 됨 

```java
static int[] bubbleSort(int arr[]) {
	int temp = 0;
	    
	for(int i = 1; i < arr.length; i++) { 
		for(int j = 0; j < arr.length-i; j++) {
			if(arr[j] > arr[j+1]) {             
				temp = arr[j];
				arr[j] = arr[j+1];
				arr[j+1] = temp;
			}
		}
	}
	return arr;
}
```
