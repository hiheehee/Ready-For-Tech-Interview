# Tree
* 나무를 거꾸로 세운 모양의 자료구조
* 노드 (Node)와 간선(Edge)로 이루어진 비선형 자료구조
* 노드의 개수 N개 => 간선은 N-1개
* 사이클 존재하지 X
---------------------------------------------------------------
# Tree 용어 정리
* Node : 트리를 구성하는 각각의 요소
* Edge : 노드와 노드를 연결하는 선
* Root Node : 트리 구조에서 최상위에 있는 노드
* Terminal Node : 하위에 다른 노드가 연결되어 있지 않은 노드
* Internal Node : 단말 노드를 제외한 모든 노드, 루트 노드 포함
* sibling : 같은 부모를 가지는 노드
* 노드의 크기 size : 자신을 포함한 모든 자손 노드의 개수
* 노드의 깊이 depth : 루트에서 특정 노드에 도달하기 위해 거쳐야 하는 간선의 수
* 노드의 레벨 level : 트리의 특정 깊이를 가지는 노드의 집합
* 노드의 차수 degree : 하위 트리 개수 / 간선 수 (degree) = 각 노드가 지닌 가지의 수
* 트리의 차수 degree of tree : 트리의 최대 차수
* 트리의 높이 height : 루트 노드에서 가장 깊숙히 있는 노드의 깊이
----------------------------------------------------------------
# Tree 종류
* 포화 이진 트리 Full Binary Tree : 모든 레벨이 꽉 찬 이진 트리, k레벨의 노드의 개수는 2^(k - 1)
* 완전 이진 트리 Complete Binary Tree : 왼쪽에서 오른쪽으로 순서대로 채워진 이진 트리
* 편향 이진 트리 Skewed Binary Tree : 오른쪽이나 왼쪽이로 편향되어 있는 이진 트리 
----------------------------------------------------------------
# Tree 순회 방식
* 전위 순회 pre-order : Root → 왼쪽 자식 → 오른쪽 자식
* 중위 순회 in-order : 왼쪽 자식 → Root → 오른쪽 자식
* 후위 순회 post-order : 왼쪽 자식 → 오른쪽 자식 → Root
-----------------------------------------------------------
```java
public class Tree<T> {
    private Node<T> root;

    public Tree(T rootData) {
        root = new Node<T>();
        root.data = rootData;
        root.children = new ArrayList<Node<T>>();
    }

    public static class Node<T> {
        private T data;
        private Node<T> parent;
        private List<Node<T>> children;
    }
}
```
