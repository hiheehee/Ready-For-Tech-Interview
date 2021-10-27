<h1><center>BFS : Breadth First Search</center></h1>
<img width="80%" src="https://user-images.githubusercontent.com/49300728/138594468-6f114ab5-17a3-4849-9346-72618f46a2a5.gif"/>  

* 시작 노드를 시작으로 인접한 노드부터 탐색하는 방법  
* 큐 사용   
* 최소 비용에 적합  
* 시간 복잡도  
  - 인접 행렬 : O(V^2)  
  - 인접 리스트 : O(V+E)  

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.Collections;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

// 백준 1260 문제 
public class Main {

	static ArrayList<Integer> al[];
	static int V, E;
	static boolean visited[];
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		V = Integer.parseInt(st.nextToken()); // 정점의 수
		E = Integer.parseInt(st.nextToken()); // 간선의 수
		int s = Integer.parseInt(st.nextToken()); // 시작 노드
		
		al = new ArrayList[V+1];
		
		for(int i = 0; i < V+1; i++) {
			al[i] = new ArrayList<>();
		}
		
		for(int i = 0; i < E; i++) {
			st = new StringTokenizer(br.readLine());
			int a = Integer.parseInt(st.nextToken());
			int b = Integer.parseInt(st.nextToken());
			
			al[a].add(b);
			al[b].add(a);
		}
		
		for(int i = 0; i < V+1; i++) {
			Collections.sort(al[i]);
		}
    
		bfs(s);
		
	}
	
	static void bfs(int s) {
		Queue<Integer> q = new LinkedList<>();
		q.add(s);
		visited = new boolean[V+1];
		
		while(!q.isEmpty()) {
			int cur = q.poll();
			if(visited[cur]) continue;
			visited[cur] = true;
			System.out.print(cur+" ");
			for(int i : al[cur]) {
				q.add(i);
			}
		}
		
	}
}

/*

입력 :

5 5 3
5 4
5 2
1 2
3 4
3 1

출력 :

3 1 4 2 5
*/

```
=====================================================================
<h1><center>DFS : Depth First Search</center></h1>
<img width="80%" src="https://user-images.githubusercontent.com/49300728/138594239-6241014e-1c89-40d0-a3d6-d9c0689f27a8.gif"/>
  
* 시작 노드를 시작으로 가장 깊은 노드까지 탐색후 다시 간선을 따라 나와 탐색하는 방법  
* 스택이나 재귀 사용   
* 모든 경우 탐색에 적합  
* 시간 복잡도  
  - 인접 행렬 : O(V^2)  
  - 인접 리스트 : O(V+E)

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.Collections;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

// 백준 1260 문제 
public class Main {

	static ArrayList<Integer> al[];
	static int V, E;
	static boolean visited[];
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		V = Integer.parseInt(st.nextToken()); // 정점의 수
		E = Integer.parseInt(st.nextToken()); // 간선의 수
		int s = Integer.parseInt(st.nextToken()); // 시작 노드
		
		al = new ArrayList[V+1];
		
		for(int i = 0; i < V+1; i++) {
			al[i] = new ArrayList<>();
		}
		
		for(int i = 0; i < E; i++) {
			st = new StringTokenizer(br.readLine());
			int a = Integer.parseInt(st.nextToken());
			int b = Integer.parseInt(st.nextToken());
			
			al[a].add(b);
			al[b].add(a);
		}
		
		for(int i = 0; i < V+1; i++) {
			Collections.sort(al[i]);
		}
    
    visited = new boolean[V+1];
		dfs(s);
		
	}
	
	static void dfs(int cur) {
		visited[cur] = true;
		System.out.print(cur+" ");
		for(int i : al[cur]) {
			if(!visited[i]) {
				dfs(i);
			}
		}
	}
}

/*
입력 :

5 5 3
5 4
5 2
1 2
3 4
3 1

출력 :

3 1 2 5 4 

*/

```
