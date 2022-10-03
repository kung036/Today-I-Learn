# **BFS, DFS**

## **트리/그래프 순회**

-   트리/그래프 순회 : 모든 노드를 한 번씩 방문하는 것
-   순회 방법 : DFS, BFS

## **깊이우선탐색(Depth-First Search, DFS)**
-   탐색방법
    1.  전위 순회(pre-order traversal) : root → Left → Right
    2.  중위 순회(in-order traversal) : Left → root → Right
    3.  후위 순회(post-order traversal) : Left → Right → root
-   크기가 클수록 깊이우선탐색이 유리
-   구현 : stack 또는 재귀

## **너비우선탐색(Breadth-First Search, BFS)**
-   탐색방법
    -   레벨 순회(level-order traversal) : 레벨 순으로 방문(level 1 → level 2 ... )
-   크기가 작을수록 너비우선탐색이 유리
-   구현 : queue