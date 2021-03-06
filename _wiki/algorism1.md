---
layout  : wiki
title   : 알고리즘
summary : 알고리즘
date    : 2021-02-26 17:11:06 +0900
updated : 2021-03-01 16:53:04 +0900
tag     : 알고리즘,정렬,기초 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

##### 주어진 배열에서 합계와 최고 값을 출력하라
```java
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
```
##### 주어진 배열의 값들을 오른쪽으로 한칸식 (shift) 하고 마지막 정수는 배열의 첫칸으로 이동하라
```java
  public static void main(String[] args) {
    int[] nums = new int[]{1,2,3,4,5};

    int lastNum = nums[nums.length - 1];
    for (int i = nums.length - 2; i >=0 ; i--) {
      nums[i+1] = nums[i];라
    }
    nums[0] = lastNum;

    for (int num : nums) {
      System.out.println(num);
    }
  }
```

##### 1~100000 사이의 소수를 모두 출력하라
```java
  public static void main(String[] args) {
    for (int n = 2; n <= 100000; n++) {
      boolean isPrime = true;
      for (int i=2; i*i < n && isPrime; i++) {
        if (n % i == 0) {
          isPrime = false;
        }
      }
      if (isPrime) {
        System.out.println(n);
      }
    }
  }
```

#####  사용자로부터 정수 n개를 입력받아 순서대로 배열에 저장하고 중복된 정수 쌍의 갯수를 카운트하여 출력하라
```java
    public static void main(String[] args) {

      Scanner kb = new Scanner(System.in);
      int n = kb.nextInt();
      int[] data = new int[n];
      for(int i = 0; i < n ; i++) {
        data[i] = kb.nextInt();
      }
      kb.close();

      int count = 0;
      for(int i = 0; i < n-1; i++) {
        for(int j = i + 1; j < n; j++) {
          if (data[i] == data[j]) {
            count++;
          }
        }
      }
      System.out.println(count);
    }
```

##### n개의 음이 아닌 한자리 정수를 입력받아 배열에 저장한 후 이들 중에서 1개 이상의 연속된 정수들을 합아여 얻을 수 있는 소수들 중에서 최댓값을 출력하라
```java
public static void main(String[] args) {
    Scanner kb  = new Scanner(System.in);
    int n = kb.nextInt();
    int[] data = new int[n];
    for (int i = 0 ; i < n; i++) {
      data[i] = kb.nextInt();
    }
    kb.close();

    int maxPrime = 0;
    for(int i = 0; i < n; i++) {
      for(int j = i; j < n; j++) {
        // convert data[i]....data[j] into an integer
        // ex 1 9 4 0 7 1 3 6 2 3
        // val = 0
        // val = 0 * 10 + 1 = 1
        // val = 1 * 10 + 9 = 19
        // val = 19 * 10 + 4 = 194
        int val = 0;
        for (int k = i; k <= j; k++) {
          val = val * 10 + data[k];
        }
        // test if is a prime
        boolean isPrime = true;
        for (int k=2; k*k <= val && isPrime; k++) {
          if (val % k == 0) {
            isPrime = false;
          }
        }

        // if yes, compare to the max
        if (isPrime && val > 1 && val > maxPrime) {
          maxPrime = val;
        }
      }
    }

    if (maxPrime > 0) {
      System.out.println(maxPrime);
    } else {
      System.out.println("No prime Number");
    }
  }
```

##### 사용자로부터 N개의 정수를 입력받은 후 오름차순으로 정렬하여 출력하라(버블)
```java
public static void main(String[] args) {
    Scanner kb = new Scanner(System.in);
    int n = kb.nextInt();
    int[] data = new int[n];
    for(int i=0; i<n; i++) {
      data[i] = kb.nextInt();
    }
    kb.close();

    for (int i=n-1; i>0 ; i--) {
      // data[0]...data[i]
      for (int j=0; j<i; j++) {
        if (data[j] > data[j+1]) {
          // swap data[j] and data[j+1]
          int tmp = data[j];
          data[j] = data[j+1];
          data[j+1] = tmp;
        }
      }
    }
    System.out.println("Sorted data");
    for (int i : data) {
      System.out.println(i);
    }
  }
```
