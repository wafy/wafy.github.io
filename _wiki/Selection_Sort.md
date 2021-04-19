---
layout  : wiki
title   : 선택 정렬(Selection Sort)
summary : 알고리즘 선택정렬
date    : 2021-04-19 19:26:43 +0900
updated : 2021-04-19 19:57:04 +0900
tag     : 알고리즘, 정렬, sort
toc     : true
public  : true
parent  : 
latex   : true 
---
* TOC
{:toc}

## 선택정렬이란?
> 데이타가 무작위로 여러 개 있을 때, 이 중에서 가장 작은 데이터를 선택해 맨 앞에 있는 데이터와 바꾸고, 그다음 작은 데이터를 선택해 앞에서 두 번째 데이터와 바꾸는 과정을 반복하는 방법 가장 원시적인 방법으로 매번 가장 작은 것을 선택한다는 의미에서 선택정렬이라고 한다.


## 시간 복잡도 
> N - 1 번 만큼 가장 작은 수를 찾아서 맨앞으로 보낸다.
매번 가장 작은 수를 찾기 위해서 비교 연산이 필요하다.

### $$ O(N^2) $$

```python

array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

for i in range(len(array)):
    min_index = i # 가장 작은 원소의 인덱스
    for j in range(i + 1, len(array)):
        if array[min_index] > array[j]:
            min_index = j
        array[i], array[min_index] = array[min_index], array[i] #python 식 스와프 

```
