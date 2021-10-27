# 순열 : Permutation
* **서로 다른 n개**의 수 중 **중복을 허용하지 않고** **r개**를 뽑아 일렬로 **나열**한 수

```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.StringTokenizer;

// 백준 15649 풀이
public class Main {

	static int n, r;
	private static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		n = Integer.parseInt(st.nextToken());
		r = Integer.parseInt(st.nextToken());
		StringBuffer sb = new StringBuffer();
		boolean visited[] = new boolean[n+1];
		
    		nPr(0, visited, sb);
    		bw.close();
	}
	
	static void nPr(int depth, boolean visited[], StringBuffer sb) throws IOException {
		if(r == depth) {
			bw.write(sb.toString()+"\n");
			return;
		}
		
		for(int i = 1; i < n+1; i++) {
			if(!visited[i]) {
				visited[i] = true;
				StringBuffer newSb = new StringBuffer(sb);
				nPr(depth+1, visited, newSb.append(i+" "));
				visited[i] = false;
			}
		}
	}
}

/*
입력 :
4 2

출력 :
1 2
1 3
1 4
2 1
2 3
2 4
3 1
3 2
3 4
4 1
4 2
4 3
*/
```

# 중복 순열
* **서로 다른 n개**의 수 중 **중복을 허용**하고 **r개**를 뽑아 일렬로 **나열**한 수
```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.StringTokenizer;

public class Main {

	static int n, r;
	private static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		n = Integer.parseInt(st.nextToken());
		r = Integer.parseInt(st.nextToken());
		StringBuffer sb = new StringBuffer();
		
		nPir(0, sb);
		bw.close();
	}
	
	static void nPir(int depth, StringBuffer sb) throws IOException {
		if(r == depth) {
			bw.write(sb.toString()+"\n");
			return;
		}
		
		for(int i = 1; i < n+1; i++) {
			StringBuffer newSb = new StringBuffer(sb);
			nPr(depth+1, newSb.append(i+" "));
		}
	}

}

/*
입력 :
4 2

출력 :
1 1 
1 2 
1 3 
1 4 
2 1 
2 2 
2 3 
2 4 
3 1 
3 2 
3 3 
3 4 
4 1 
4 2 
4 3 
4 4
*/
```

# 조합 : Combination
* **서로 다른 n개**의 수 중 **중복을 허용하지 않고** **r개**를 뽑은 수
```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.StringTokenizer;

public class Main {

	static int n, r;
	private static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		n = Integer.parseInt(st.nextToken());
		r = Integer.parseInt(st.nextToken());
		StringBuffer sb = new StringBuffer();
		boolean visited[] = new boolean[n+1];
		
		nCr(0, 1, visited, sb);
		bw.close();
	}
	
	static void nCr(int depth, int start, boolean visited[], StringBuffer sb) throws IOException {
		if(r == depth) {
			bw.write(sb.toString()+"\n");
			return;
		}
		
		for(int i = start; i < n+1; i++) {
			if(!visited[i]) {
				visited[i] = true;
				StringBuffer newSb = new StringBuffer(sb);
				nCr(depth+1, i+1, visited, newSb.append(i+" "));
				visited[i] = false;
			}
			
		}
	}

}
/*
입력 :
4 2

출력 :
1 2 
1 3 
1 4 
2 3 
2 4 
3 4 
*/
```

# 중복 조합
* **서로 다른 n개**의 수 중 **중복을 허용**하고 **r개**를 뽑은 수
```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.StringTokenizer;

public class Main {

	static int n, r;
	private static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
	public static void main(String[] args) throws IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		n = Integer.parseInt(st.nextToken());
		r = Integer.parseInt(st.nextToken());
		StringBuffer sb = new StringBuffer();
		nHr(0, 1, sb);
		bw.close();
	}
	
	static void nHr(int depth, int start, StringBuffer sb) throws IOException {
		if(r == depth) {
			bw.write(sb.toString()+"\n");
			return;
		}
		
		for(int i = start; i < n+1; i++) {
			StringBuffer newSb = new StringBuffer(sb);
			nHr(depth+1, i, newSb.append(i+" "));
		}
	}

}


/*
입력 : 
4 2

출력 : 
1 1 
1 2 
1 3 
1 4 
2 2 
2 3 
2 4 
3 3 
3 4 
4 4
*/
```
