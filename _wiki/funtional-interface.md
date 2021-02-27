---
layout  : wiki
title   : 
summary : 
date    : 2021-02-27 22:07:55 +0900
updated : 2021-02-27 22:23:08 +0900
tag     : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

#### 대표 함수형 인터페이스
|인터페이스명|메서드명|내용
|---------------|-------------------|-----------------------------------------|
| Consumer<T>   | void accep(T t)   | 결과를 리턴하지 않을때                  |
| Function<T,R> | R apply(T t)      | 파라미터를 다른값으로 변환해서 반환할때 |
| Predicate<T>  | boolean test(T t) | true/false를 반환할때                   |
| Suppier<T>    | T get()           | 파라미터 없이 리턴값만 있을때           |



