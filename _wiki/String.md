---
layout  : wiki
title   : String 클래스 
summary : Java String 클래스의 대해서 정리하자
date    : 2021-03-16 15:15:58 +0900
updated : 2021-03-16 16:17:30 +0900
tag     : String
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## String 클래스의 정의
- 문자열을 나타내는 것이 java.lang. 패키지에 소속된 String 클래스이다. 기본자료형이 아니다.[^Doit-71]
- String 클래스에는 문자열을 저장하기 위해서 문자열 배열 변수(char[]) value를 인스턴드 변수로 정의해 놓고 있다.
인스턴트 생성시 생성자의 매개변수로 입력받는 문자열은 인스턴트 변수(value)의 문자열 배열(char[])로 저장된다.[^FormulaOfJava-376] 

```
public final class String
    implements java.io.Serializable, Comparable<String>, CharSequence {
```
- final로 선언되어 있다. 더이상 클래스를 확장할 수 없다.

```
String s = "ABC";
```
- 변수 s가 참조하는 곳은 단순한 문자열이 아니라 문자열을 내부에 가진 인스턴트 임을 기억해두자.[^Doit-71]

## 기억해둬야할 기본 메서드
```
char charAt(int i) // 인덱스가i인 곳의 문자를 가져옵니다.
int length() //문자열의 문자 수를 가져옵니다.
boolean equals(String s) //문자열의 s와 같은가를 조사합니다.
```


## 참고문헌

- [Doit] 자료구조와 함께 배우는 알고리즘 입문자 자바편 / Bohyoh Shibata 저 / 강민 역 / 이지스퍼블링
- [GodOfJava] 자바의 신 1편 / 이상민 저 / 로드북
- [FormulaOfJava] 자바의 정석 / 남궁민 저/ 도우출판

## 주석

[^Doit-71]:[Doit] 02. 기본 자료구조. 71쪽.
[^FormulaOfJava-376]:[FormulaOfJava] Chapter9장. 376쪽.
