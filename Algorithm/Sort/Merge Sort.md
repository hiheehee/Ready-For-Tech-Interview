# Merge Sort
<img width="80%" src="http://www-scf.usc.edu/~zhan468/public/Notes/resources/CDDA3F11C6EFBC01577F5C29A9066772.gif"/>  

* 분할 정복(Divide and Conquer)을 통해 정렬하는 알고리즘
* 쪼갤 수 있을 만큼 쪼개고 -> 정렬
* not 제자리 정렬 => 메모리 낭비 
* 안정 정렬(stable Sort)
* 시간 복잡도 : O(nlogn) <= 최선, 평균, 최악 모두
* 방법
  1. 리스트의 길이가 1보다 큰 경우 정렬되지 않은 리스트를 절반으로 나눠 두개의 리스트로 분할
  2. 각 리스트를 재귀적으로 합병 정렬을 이용해 정렬
  3. 두 리스트를 다시 하나의 정렬된 리스트로 합병
  4. 리스트의 길이가 1보다 작으면 이미 정렬 되었다고 생각

```java
// 분할
public ArrayList<Integer> mergeSplit(ArrayList<Integer> al) {
		if(al.size() <= 1) return al;
    
		int midIdx = al.size() / 2;
		ArrayList<Integer> left = mergeSplit(new ArrayList<Integer>(al.subList(0, midIdx)));
		ArrayList<Integer> right = mergeSplit(new ArrayList<Integer>(al.subList(midIdx, al.size())));
		return merge(left, right);
}
	
public ArrayList<Integer> merge(ArrayList<Integer> leftList, ArrayList<Integer> rightList) {
		ArrayList<Integer> mergedList = new ArrayList<Integer>();
		int leftPoint = 0;
		int rightPoint = 0;
		
		// case 1 : left, right List 둘다 있을때
		while(leftPoint < leftList.size() && rightPoint < rightList.size()) {
			if(leftList.get(leftPoint) < rightList.get(rightPoint)) {
				mergedList.add(leftList.get(leftPoint));
				leftPoint++;
			}else {
				mergedList.add(rightList.get(rightPoint));
				rightPoint++;
			}
		}
		
		// case 2 : 왼쪽 데이터만 남은 경우
		while(leftPoint < leftList.size()) { 
			mergedList.add(leftList.get(leftPoint));
			leftPoint++;
		}
		
		// case 3 : 오른쪽 데이터만 남은 경우
		while(rightPoint < rightList.size()) {
			mergedList.add(rightList.get(rightPoint));
			rightPoint++;
		}
    
		return mergedList;
}
```
