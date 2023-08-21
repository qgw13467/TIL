# AOP

- 공통 관심하를 분리하여 코드의 관리를 수월하게 함
- 스프링의 AOP는 프록시클래스가 타켓 클래스를 멤버변수로 가진 다음 공통 관심사 사이 멤버의 메소드 호출
- 따라서 private 메소드에 AOP를 적용할 수 없다.



### AOP 구현
```java
@Component
@Aspect
@Log4j2
public class TimeTrace {
    @Around("@annotation(TimeTracer)")
    public Object logTime(ProceedingJoinPoint proceedingJoinPoint) throws Throwable {

        Long start = System.currentTimeMillis();
        log.info("start: {}, {}", start, proceedingJoinPoint.toString());

        try {
            return proceedingJoinPoint.proceed();
        } finally {

            log.info("end: {}, {}", System.currentTimeMillis() - start, proceedingJoinPoint.toString());
        }
    }
}
```

### 인터페이서 정의
```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface TimeTracer {
}
```