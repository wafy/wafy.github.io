Mockito Stub
===


```
org.mockito.exceptions.misusing.InvalidUseOfMatchersException: 
Invalid use of argument matchers!
2 matchers expected, 1 recorded:
-> at com.kurly.cloud.api.coupon.order.document.OrderCouponDocumentTest.test1(OrderCouponDocumentTest.java:115)

This exception may occur if matchers are combined with raw values:
    //incorrect:
    someMethod(anyObject(), "raw String");
When using matchers, all arguments have to be provided by matchers.
For example:
    //correct:
    someMethod(anyObject(), eq("String by matcher"));

For more info see javadoc for Matchers class.

```


```
2 matchers expected, 1 recorded:
```
두개의 매처가 와야하는데 1개만 처리되었다는 뜻이다.

```
given(anyThingController.getAnyThingList(eq(1L), eq(parameterObject))).willReturn(returnList);

```
`eq` 메서드를 사용하여 파라미터를 넘겨주면 해결된다.