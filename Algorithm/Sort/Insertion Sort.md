# Insertion Sort
<img width="80%" src="https://miro.medium.com/max/724/1*lOADpUyGCRe2VC7Rl7HV9g.gif">    
* 2번째 원소에서 시작하여 왼쪽 원소들과 비교해 삽입할 위치를 지정하고 삽입할 위치 다음의 원소들을 모두 오른쪽으로 옮긴뒤 자료를 삽입하여 정렬하는 알고리즘  
* Selection Sort과 유사  
* 흔히 손 안의 카드를 정렬이라 불림  
* 제자리 정렬(in-place sorting)  
* 시간 복잡도 : 최선 O(N), 평균, 최악 : O(N^2)  
* 공간 복잡도 : O(N)  
* 방법  
  1. 2번째 위치부터 시작 => i  
  2. 앞의 위치의 값이 현재 위치의 값보다 크다면 뒤로 한칸씩 이동 => prev   
  3. 앞의 위치의 값이 현재 위치의 값보다 작거나 더이상 앞으로 가지 못하는 경우라면 해당 위치에 현재 값 삽입  

```java
static int[] insertionSort(int[] arr) {
  for(int i = 1 ; i < arr.length ; i++){
    int temp = arr[i];
    int prev = i - 1;
    while( (prev >= 0) && (arr[prev] > temp) ) {
      arr[prev + 1] = arr[prev];
      prev--;
    }
    arr[prev + 1] = temp;
  }
  return arrr;
}
```
