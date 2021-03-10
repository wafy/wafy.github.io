---
layout  : wiki
title   : 빅오(Big-O)표기법 
summary : 빅오표기법
date    : 2021-03-09 16:37:07 +0900
updated : 2021-03-09 17:27:04 +0900
tag     : 빅오, bigo
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

### Big-O란?
- 알고리즘의 성능을 수학적으로 표현한 표기법
- 알고리즘의 시간과 공간 복잡도를 표현 
- 데이타나 사용자의 증가율에 따른 알고리즘 성능을 측정하는게 목표이므로 상수시간은 1이된다.

#### O(1)
>> 데이타의 크기와 상관없이 언제나 일정시간이 걸리는 알고리즘 

```
    // 입력받은 데이타의 크기와 상관없이 언제나 배열의 0번째 데이타를 반환하는 예
    F(int[] n) {
        return (n[0] == 0) ? true: false;
    }
```

#### O(n)
>> 입력데이타의 크기에 비례해서 처리시간이 걸리는 알고리즘 

```java
   // 입력받은 데이타의 크기만큼 반복하는예
   F(int[] n) {
        for( i=0; i < n.length; i++) {
            System.out.println(i);
    }
```

#### O(n^2)
>> 데이타가 많아질수록 처리 시간은 수직 상승한다.

```
    F(int[] n) {
        for (int i=0; i<n.length; i++) {
            for(int j=0; j<n.length; j++) {
                print i+j;
            }
        }
    }
```

#### O(nM)
>> m을 n만큼 돌려준다.데이타가 증가할수록 수직에 가까운 그래프가 된다.
```
    F(int[] n, int[] m) {
        for (int i=0; i<n.length;i++) {
            for(int j=0; j<m.length;j++) {
                pritn i+j;
            }
        }
    }
```

#### O(n^3)
>>> 데이타가 증가함에 따라 급격하게 처리시간이 걸린다.
``` 
    F(int[] n) {
        for (int i = 0; i< n.length; i++) {
            for (int j=0; j<n.length: j++) {
                for (int k=0; k<n.length; k++) {
                    print i+ j +k;
                }
            }
        }
     }
```

#### O(2^n)
>>> 피보나치 수열 

```
    F(n, r) {
        if (n <=0) return 0;
        else if (n == 1) return r[n] = 1;
        return r[n] = F(n-1,r) + F(n-2,r);
    }
```

### O(m^n)

### O(log n)
>> 대표적인 알고리즘은 이진검색, 조회할때마다 처리해야할 데이타의 양이 절반으로 줄어드는 알고리즘
>> 데이타가 증가해도 성능의 영향이 없고 O(n)보다도 처리시간이 빠르다.
```
    F(k, arr, s, e) {
        if (s > e) return -1;
        m = (s + e) / 2;
        if (arr[m] == k) return m;
        else if (arr[m] > k) return F(k, arr, s, m-1);
        else return F(k,arr,m+1,e);
    }
```

### O(sqirt(n))
>> 루트100의 제곱근은 10 루트9의 제곱은은 3 과 같은 형식으로 제곱근만큼만 확인하는 알고리즘 







