---
layout  : wiki
title   : 함수구문의 종류
summary : 
date    : 2022-01-11 22:26:57 +0900
updated : 2022-01-12 09:01:58 +0900
tag     : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## 함수의 종류(작성중)

### 일급 클래스 함수

- 일급 클래스 함수란? 컬랙션이 함수로 기능할 수 있지만 반대로 함수도 데이터로 기능할 수 있다.
- 자바는 모든 행위를 클래스의 인스턴스 또는 인스턴스에 덧붙여진 형태로 모델링됨 
- 함수형에서는 소프트웨어 개발 문제에 대해 함수를 데이터에 적용하는 관점으로 인식

#### 일급 클래스 함수 
- 자바의 익명클래스로 이해하고자 하지 말것 
- 다른 함수들과 합성(composition)의 예
```clojure

(def fifth (comp first rest rest rest rest ))
(fifth [1 2 3 4 5])
;=> 5
```
한줄의 여러개의 괄호를 열게 되는 경우는 그리 많지 않치만 이런 경우 대부분 새로운 함수를 생성하고 
리턴하여 바로 호출하려는 의도로 이해해야한다.
```clojure

(defn fnth [n]
  (apply comp
         (cons first (take (dec n) (repeat rest)))))
;=> e         
```

```clojure
(map (comp ;함수구성
       keyword ;키워드생성
       #(.toLowerCase %) ;소문자로 변환
       name); 이름을 string으로 리턴
     '(a B C)) ;합성한 함수를 심벌의 리스트에 맵핑
;=> (:a :b :c)     
```
함수를 잘게 쪼개고 각 조각을 잘 정의하면 결합성(composablity)가 향상되고 결국 재사용성이 향상되는 결과를 얻을 수 있다.


### 합성

### 부분적평가

### 재귀

### 렉시컬 클로저(lexical closure)

### 순수함수

### 함수 제약

### 고차 함수

