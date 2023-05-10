... 파라미터
===
메소드의 파라미터를 가변적으로 받아 처리할 수 있으며, List타입이 아닌 [ ]배열을 통해서도 파라미터를 전달할 수 있다

```agsl
    method(Object ...)
    
    // ,를 통한 인자 전달
    method(obj1, obj2);
    
    //배열을 통한 인자 전달
    Objectp[] objs = {obj1, pbj2};
    method(objs);

```