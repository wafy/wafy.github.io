---
layout  : wiki
title   : Object 클래스
summary : java.lang.object
date    : 2021-03-17 10:54:11 +0900
updated : 2021-03-18 07:52:12 +0900
tag     : object
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

java.lang 패키지는 자바프로그램에 가장 기본이 되는 클래스를 포함하고 있고 import문없이 사용할 수 있다.

## Object class
>  모든 클래스의 최고 조상이기 때문에 Object클래스의 맴버들은 모든 클래스에서 바로 사용 가능하다.
> Object클래스는 맴버변수는 없고 8개의 메서드만 가지고 있다.

## equals method
매개변수로 객체의 참조변수를 받아서 비교하여 그 결과를 boolean값으로 알려준다.
그렇기 때문에 서로 다른 두 객체를 equals 메서드로 비교하면 항상 fasle를 결과로 얻게 된다.

```
 public boolean equals(Object obj) {
    return this == obj;
  }
```

```
public class EqualsEx1 {

  public static void main(String[] args) {
    Value v1 = new Value(10);
    Value v2 = new Value(10);
    if(v1.equals(v2)) {
      System.out.println("같다");
    } else {
      System.out.println("다르다");
    }

    v2 = v1;
    if(v1.equals(v2)) {
      System.out.println("같다");
    } else {
      System.out.println("다르다");
    }
  }
}

class Value {
  int value;
  Value(int value) {
    this.value = value;
  }
}

다르다
같다
```
> equals 메서드는 주소값으로 비교를 하기 때문에, 두 Value인스턴스의 맴버변수 value의 값이 같을지라도 equals로 비교한 결과는 false이다.
> Object클래스로부터 상속받은 equals메서더는 결국 두개의 참조변수가 같은 객체를 참조하고 있는지 즉 두 참조변수에 저장된 값(주소값)

```
import java.util.Objects;

public class EqualsEx1 {

  public static void main(String[] args) {
    Value v1 = new Value(10);
    Value v2 = new Value(10);
    if(v1.equals(v2)) {
      System.out.println("같다");
    } else {
      System.out.println("다르다");
    }

    v2 = v1;
    if(v1.equals(v2)) {
      System.out.println("같다");
    } else {
      System.out.println("다르다");
    }
  }
}

class Value {
  int value;
  Value(int value) {
    this.value = value;
  }

  @Override
  public boolean equals(Object o) {
    if (this == o) {
      return true;
    }
    if (o == null || getClass() != o.getClass()) {
      return false;
    }
    final Value value1 = (Value) o;
    return value == value1.value;
  }
}

같다
같다
```

> String 클래스도 Object클래스의 equals메서드를 오버라이딩을 통해서 String 인스턴스가 갖는 문자열 값을 비교하도록 되어있다. 그렇기 때문에 같은 내용의 문자열을 갖는 두 String 인스턴스에 equasl메서드를 사용하면 핫아 true값을 얻는 것이다.


## hashCode method
> 각 인스턴스의 같고 다름을 비교하기 위한 인스턴스 구별 값인 해쉬코드를 반환한다.
> 서로 다른 종류의 인스턴스를 구분할 공통기준이 해쉬코드(주소값)외에는 없기 때문에 인스턴스의 맴버변수의 값들을 비교하는 것보다는 4byte의 해쉬코드값을 비교하는 것이 더 빠르기 때문이다.

## toString method
> 인스턴스에 대한 정보를 문자열로 제공할 목적이다.

```
public String toString() {
      return getClass().getName() + "@" + Integer.toHexString(hashCode());
}
```
> toString을 그대로 사용할경우 16진수의 해쉬코드를 얻게 될것이다.
> 해쉬코드는 인스턴스의 주소와 관련된 값으로, 서로 다른 인스턴스는 서로 다른 해쉬코드값을 가질 것을 보장한다
> 보통 인스턴스나 클래스에 대한 정보 또는 인스턴스 변수들의 값을 문자열로 변환하여 반환하도록 오버라이딩된다.

## clone method
> 자신을 복제하여 새로운 인스턴스를 생서하는 일을 한다.
> 단순히 맴버변수의 값만을 복사하기 때문에 배열이나 인스턴스가 맴버로 정의되어 있는 클래스의 인스턴스는 완전한 복제가 이루어지 않는다.



