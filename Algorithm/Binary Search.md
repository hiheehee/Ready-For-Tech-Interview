# 이분 탐색 : Binary Search
* 탐색의 범위를 두 부분으로 나누어 탐색하는 방법
* 두 부분으로 나눠 탐색하기 때문에 선형 탐색보다 빠르다.
* but 탐색하고자 하는 원소들이 이미 정렬이 되어있어야 한다.

* 시간복잡도
선형 탐색 : O(N)
이분 탐색 : O(logN)

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ15656 {
	static int nums[];
	static int n, target;
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		n = Integer.parseInt(st.nextToken());
		target = Integer.parseInt(st.nextToken());
		nums = new int[n];
		
		st = new StringTokenizer(br.readLine());
		for(int i = 0; i < n; i++) nums[i] = Integer.parseInt(st.nextToken());
		
		int answer = binarySearch();
		System.out.print(answer == -1? "해당 원소 존재하지 않음": answer+"번째 인덱스 값 : " + nums[answer]);
		
	}
	
	 static int binarySearch() {
	      int left = 0, right = nums.length - 1;
	      
	      while (left <= right) {
	          int mid = (left + right) / 2;
	          if (nums[mid] == target) return mid;
	          else if (nums[mid] > target) right = mid - 1;
	          else left = mid + 1;
	      }
	      
	      return -1;
	  }

}
/*
입력 : 
5 19
1 5 6 19 23

출력 : 
3번째 인덱스 값 : 19
*/
```
