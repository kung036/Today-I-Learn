# 그래프(Graph)

## **그래프(Graph)**

-   여러 정점들을 간선으로 연결해서 관계를 표현한 자료구조
-   구조
    -   직접적인 관계 : 두 정점이 하나의 간선으로 연결된 관계
    -   간접적인 관계 : 두 정점이 여러 개의 간선으로 연결된 관계
-   표현 방식
    1.  인접 행렬
        -   정점의 인접한 상태를 표현한 2차원 배열
        -   사용 : 두 정점 사이의 인접 관계 확인, 가장 빠른 경로(shortest path) 구할 때
        -   ex) int\[\]\[\] edges = new int\[\]\[\] { {0, 0, 1}, {1, 0, 1}, { 1, 0, 0 } };
    2.  인접 리스트
        -   정점의 인접한 상태를 리스트로 표현
        -   메모리를 효율적으로 사용하고 싶을 때
        -   ex) int\[\]\[\] edges = new int\[\]\[\] { { 1, 2 }, { 3 }, { 0, 1 }, { } };
<br></br>  
- 용어
    -   정점(vertex) : 데이터(= 노드)
    -   간선(edge) : 정점을 연결하는 선
    -   인접(adjacency) : 두 정점이 하나의 간선으로 연결된 경우
    -   인접 정점(adjacent vertex) : 직접적인 관계에 있는 정점들
    -   가중치 그래프(weighted graph) : 간선에 비중을 둔 그래프
    -   비가중치 그래프(unweighted graph) : 모든 간선이 동일한 비중을 가진 그래프
    -   무(방)향 그래프(undirected graph) : 간선에 방향이 없는 그래프(= 일시 무향, 무향, 무방향)
    -   단방향 그래프(directed graph) : 간선에 방향이 정해진 그래프(= 일시 방향, 방향)
    -   진입차수(in-degree) : 한 정점으로 들어오는 간선의 개수
    -   진출차수(out-degree) : 한 정점에서 나가는 간선의 개수
    -   자기 루프(self loop) : 정점 자신이 다른 정점을 거치지 않고 자신에게 되돌아 오는 경우
    -   사이클(cycle) : 한 정점이 다른 정점들을 거쳐서 다시 정점으로 돌아갈 수 있는 경우

<p align="center">
  <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbA0kur%2FbtrNAxpxU7S%2F7MbIOwIHL5tkKGkbhCRmdK%2Fimg.png" alt="Graph"/>
</p>