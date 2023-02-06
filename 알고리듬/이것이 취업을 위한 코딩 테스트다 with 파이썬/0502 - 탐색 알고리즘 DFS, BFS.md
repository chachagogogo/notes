## 인접 행렬, 인접 리스트

### 장단점
|             | 장점                   | 단점                   |
| ----------- | ---------------------- | ---------------------- |
| 인접 행렬   | 노드 간 연결 확인 빠름 | 메모리 사용 비효율적   |
| 인접 리스트 | 메모리 사용 효율적     | 노드 간 연결 확인 느림 |

다음과 같은 자료가 있다고 하자.

![[Pasted image 20230206212050.png]]
이를 표현하는 방법으로 `인접 행렬`과 `인접 리스트`가 있다.

### 인접 행렬

```python
INF = 999999999

graph = [
	[0, 7, 5],      # node 0
	[7, 0, INF],    # node 1
	[5, INF, 0],    # node 2
]
```

### 인접 리스트
각 노드마다 (인접한 노드, 간선 개수) 꼴로 표기한다
```python
#[node 0, node 1, node 2]
li = [[(1, 7), (2, 5)], [(0, 7)], [(0, 5)]]
```


## DFS
1. 탐색 시작 노드를 스택에 넣고 방문 처리
2. 
	1. 스택의 최상단 노드에 미방문 인접 노드가 있으면: 미방문 인접 노드를 스택에 넣고 방문 처리
	2. 미방문 인접 노드가 없으면: 스택에서 최상단 노드 꺼내기
3. 2번을 반복

![[Pasted image 20230206213205.png]]

- 스택으로 구현. 즉 재귀 함수 사용 가능
- 1 -> 2 -> 7 -> 6 -> 8 -> 3 -> 4 -> 5
- O(N)

```python
graphList = [  
    [],         # 0인 노드는 없으므로 빈 리스트  
    [2, 3, 8],  # 1  
    [1, 7],     # 2  
    [1, 4, 5],  # 3  
    [3, 5],     # 4  
    [3, 4],     # 5  
    [7],        # 6  
    [2, 6, 8],  # 7  
    [1, 7],     # 8  
]  
  
visitedList = [False] * 9  # 0에서 8까지니깐 9  
  
def dfs(graph, v, visited):  
    visited[v] = True  
    print(v, end=" ")  
    for i in graph[v]:  
        if not visited[i]:  
            dfs(graph, i, visited)  
  
  
dfs(graphList, 1, visitedList) # 1 2 7 6 8 3 4 5 

```


### BFS
- 큐로 구현
- O(N)
- deque를 쓸 것
- 보통 DFS보다 빠름

1. 시작 노드를 큐에 넣고 방문 처리
2. 큐에서 노드를 꺼내 해당 노드의 미방문 인접 노드를 모두 큐에 넣고 방문 처리
3. 2를 반복

![[Pasted image 20230206213205.png]]

1 -> 2 -> 3 -> 8 -> 7 -> 4 -> 5 -> 6

```python
from collections import deque  
  
graphList = [  
    [],  # 0인 노드는 없으므로 빈 리스트  
    [2, 3, 8],  # 1  
    [1, 7],  # 2  
    [1, 4, 5],  # 3  
    [3, 5],  # 4  
    [3, 4],  # 5  
    [7],  # 6  
    [2, 6, 8],  # 7  
    [1, 7],  # 8  
]  
  
visitedList = [False] * 9  # 0에서 8까지니깐 9  
  
def bfs(graph, start, visited):  
    queue = deque([start])  
    visited[start] = True  
    while queue:  
        v = queue.popleft()  
        print(v, end=" ")  
        for i in graph[v]:  
            if not visited[i]:  
                queue.append(i)  
                visited[i] = True

bfs(graphList, 1, visitedList) # 1 2 3 8 7 4 5 6 
```

