---
layout  : wiki
title   : 알고리즘
summary : 알고리즘
date    : 2021-02-26 17:11:06 +0900
updated : 2021-02-26 17:11:06 +0900
tag     : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

### 주어진 배열에서 합계와 최고 값을 출력하라
```java
public class MaxNumber {

  public static void main(String[] args) {
    int[] arrays = new int[]{1, 4, 5, 6, 7, 2};

    int sum = 0;
    int max = arrays[0];
    for(int num: arrays) {
      sum += num;
      if (num > max) {
        max = num;
      }
    }
    System.out.println("sum :"+ sum);
    System.out.println("max :"+ max);
  }

}
```
