# 트리(Tree)

## **트리(Tree)**

-   사이클이 없는 그래프 구조(그래프의 일종)
-   비선형 구조, 무뱡항 계층적 자료구조
-   용어
    -   노드(Node) : 각각의 데이터
    -   루트(Root) : 트리 구조를 시작하는 노드
    -   부모 노드(Parent Node) : 상하관계에 있는 두 노드 중 상대적으로 루트에 가까운 노드
    -   자식 노드(Child Node) : 상하관계에 있는 두 노드 중 상대적으로 루트에 먼 노드
    -   형제 노드(Sibling Node) : 같은 레벨에 있는 노드
    -   리프 노드(Leaf Node) : 자식이 없는 노드
    -   간선(Edge) : 노드와 노드를 연결한 선
    -   깊이(Depth) : 루트를 기준으로 아래로 내려가는 깊이 표현
    -   레벨(Level) : 같은 깊이를 묶어서 레벨로 표현
    -   높이(Height) : 리프 노드를 기준으로 위로 올라가는 높이 표현
    -   서브 트리(Sub Tree) : 전체 트리 구조에서 트리 구조를 갖춘 작은 트리 구조

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdvM6pd%2FbtrM7kRk3z5%2FSaorGkXkaXUHHjiOApaD0K%2Fimg.png" alt="Tree"/>
</p>

## **이진탐색트리(Binary Search Tree, BST)**

-   **이진트리(Binary Tree)**
    -   자식 노드가 최대 두 개인 트리 구조
    -   종류
        -   정이진트리(full binary tree) : 각 노드는 자식 노드로 0개 또는 2개를 가지는 트리
        -   포화이진트리(perfect binary tree) : 모든 리프 노드의 레벨이 동일하고, 각 레벨이 전부 채워진 트리
        -   완전이진트리(Complete binary tree) : 마지막 레벨을 제외한 노드들으 전부 채워져있고, 마지막 레벨의 노드는 최소 왼쪽은 전부 채워진 상태의 트리
<br><br/>
- **이진탐색트리(Binary Search Tree)**
    -   왼쪽 자식들의 값은 루트보다 작고, 오른쪽 자식들의 값은 루트보다 큰 특징을 가지는 이진트리
    -   값 삽입/삭제 시 균형 틀어짐으로 인한 탐색 시간 증가 문제가 발생 가능 → 삭제/삽입 시 트리 구조 재조정하는 과정 필요