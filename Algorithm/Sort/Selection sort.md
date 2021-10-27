# Selection sort
<img width="80%" src="https://miro.medium.com/max/724/1*sBC4znJwu6ZzhJ7h5OYSTg.gif"/>  

* 순서 마다 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택해  알고리즘 
* 제자리 정렬(in-place sorting)
* 불안정 정렬(Unstable Sort)
* 시간 복잡도 : O(N^2) <= 최선, 평균, 최악 모두
* 공간 복잡도 : O(N)
* 방법
  1. 배열의 첫번째부터 맨 끝으로 이동하며 원소를 넣을 위치를 선정 => i
  2. 원소를 넣을 위치 이후의 값 중 최소값을 찾아 선정한 위치의 값과 교체

```java
static int[] selectionSort(int arr[]) {
        for (int i = 0; i < arr.length; i++) {
            int standard = i;
            for (int j = i+1; j < arr.length; j++) {
                if (arr[j] < arr[standard]) standard = j;
            }
          	
            int temp = arr[standard];
            arr[standard] = arr[i];
            arr[i] = temp;
        }
        return arr;
}
```
