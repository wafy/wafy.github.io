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

### 주어진 배열의 값들을 오른쪽으로 한칸식 (shift) 하고 마지막 정수는 배열의 첫칸으로 이동하라
```java
  public static void main(String[] args) {
    int[] nums = new int[]{1,2,3,4,5};

    int lastNum = nums[nums.length - 1];
    for (int i = nums.length - 2; i >=0 ; i--) {
      nums[i+1] = nums[i];
    }
    nums[0] = lastNum;

    for (int num : nums) {
      System.out.println(num);
    }
  }
```
