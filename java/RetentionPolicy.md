# RetentionPolicy

---

 자바의 어노테이션에는 3가지의 라이프 사이클이 있다.
- RetentionPolicy.SOURCE
    - 소스코드 java 까지 남아있다
    - 롬복의 @Getter와 같은 어노테이션들은 컴파일될 때 사라진다.
    - 바이트코드에 getter에 해당하는 코드가 생성된다.


- RetentionPolicy.CLASS
  - 런타임에서 클래스로드가 해당 클래스를 읽어오면 사라진다.
  - 롬복의 @NotNull이 해당한다.
  - Maven / Gradle로 받은 라이브러리와 같은 jar파일은 .class파일만
  포함되어있기 때문에 타입체커, IDE부가기능 등을 사용하기 위해 해당 정책을 사용한다.
  

- RetentionPolicy.RUNTIME
  - 런타임에서 Reflection API 등을 사용해서 어노테이션 정보를 가져갈 수 있다.
  - 스프링의 @Controller 등의 어노테이션이 실행중인 시점에 컴포넌트 스캔이 가능하다.
