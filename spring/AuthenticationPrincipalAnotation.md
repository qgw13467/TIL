@AuthenticationPrincipal
===

- SecurityContextHolder에서 인증객체를 가져온다.
- 인증이 안된다면 anonumous인증객체가 주입되어있다
- 따라서 인증이 되지 않은 객체를 가져올 시 Object로 받아 타입이 String인지 확인 필요