# Trie
* 일반적인 Tree 구조
* 문자열 저장 및 탐색에 유용한 자료구조
* Trie = Digtal Tree = Radix Tree = Prefix Tree
* 자식노드 Map<key, value> 형태
* 루트를 제외한 노드의 자손들은 해당 노드와 공통 접두어 
* 루트 노드는 빈 문자와 연관

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.HashMap;
import java.util.Map;

public class Main {
	static boolean check;
	public static void main(String[] args) throws IOException{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int t = Integer.parseInt(br.readLine());
		
		while(t-- > 0) {
			check = true;
			int n = Integer.parseInt(br.readLine());
			Node root = new Node();
			String words[] = new String[n];
			
			for(int i = 0; i < n; i++) {
				words[i] = br.readLine();
			}
			
			for(String s : words) { 
				insert(root, s); 
			}
			
			for(String s : words) { 
				check(root, s);
				if(!check) {
					break;
				}
			}
			
			if(check) {
				System.out.println("YES");
			}else {
				System.out.println("NO");
			}
		}

	}
		
	static void check(Node cur, String s) {
		char str[] = s.toCharArray();
		for(int i = 0; i < str.length; i++) {
			cur = cur.children.get(str[i]);
			if(i != str.length-1 && cur.check) {
				check = false;
				return;
			}
		}
	}
	
	static void insert(Node cur, String s) {
		char str[] = s.toCharArray();
		for(int i = 0; i < str.length; i++) {
			cur = cur.children.computeIfAbsent(str[i], l -> new Node());
			if(i == str.length-1) {
				cur.check = true;
			}
		}
	}
	
	static class Node{
		Map<Character, Node> children;
		boolean check;
		
		Node(){
			children = new HashMap<>();
		}
	}

}
```
