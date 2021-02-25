---
layout: post
title: my-first-post
date: 2020-02-25 10:40:00 +0900
category: algorithms
---
# [Greedy] Q5. 볼링볼 고르기
> 내가 푼 방식

```python
n, m = map(int, input().split())
weights = list(map(int, input().split())) 
result = 0

for i in range(0, n-1):
    for j in range(i, n):
        if weights[i] != weights[j]:
            result += 1

print(result)
```

문제에서 두 사람은 서로 무게가 다른 볼링공을 고르기로 했기 때문에, 무게가 다른 경우에는 result에 1씩 추가시켜 주었다. 시간복잡도는 O(n^2)이다.


> 답안지

```python
n, m = map(int, input().split())
data = list(map(int, input().split()))
array = [0] * 11

for i in data:
    array[x] += 1

result = 0
for i in range(1, m+1):
    n -= array[i]
    result += array[i] * n

print(result)
```

공의 무게는 1 이상 10 이하이기 때문에 인덱스로 전부 접근할 수 있도록 공의 무게를 저장하는 array 리스트의 크기를 11로 한다. 예를 들어 무게 1인 볼링골이 있을 때,&nbsp;array[1]이 1 증가한다.&nbsp;두번째 for문에서 i는 첫번째 사람이 고른 볼링공의 무게라고 보면 된다.&nbsp; 자신의 무게와 같은 볼링공은 고를 수 없기 때문에 for문에서 n에서 첫번째 사람이 고른 볼링공의 개수는 빼준다. 첫번째 사람이 고를 수 있는 볼링공의 수와 두번째 사람이 고를 수 있는 볼링공의 수를 곱하여 result에 더해주면 첫번째 사람이 무게 i의 볼링공을 골랐을 경우 가능한 경우의 수를 더해주는 셈이 되므로 답을 구할 수 있다. 시간복잡도는 O(m)이다.