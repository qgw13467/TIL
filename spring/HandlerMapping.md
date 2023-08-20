1. 컨트롤러를 처리하기 전에 어댑터는 ArgumentResolver에 요청을 해 컨트롤러에서 필요한 파라미터를 요청한다.
2. ArgumentResolver는 Controller를 보고 파라미터를 찾는다.
3. 핸들러 어댑터에게 파라미터를 반환한다.
4. 핸들러 어댑터는 파라미터를 가지고 컨트롤러를 처리한다.
5. 컨트롤러를 처리하고 결과 값을 HandlerMethodReturnValueHandler 인터페이스를 걸쳐서 처리한다.(ex) @ResponseBody, String, ModelAndView)
6. 여기서 HandlerMethodReturnValueHandler를 통해서 반환하는 이유는 다양한 타입을 처리하기 위해서이다.

- 실제로 @RequestParam은 RequestParamMethodArgumentResolver가 동작하고, @ReqeustBody는 RequestResponseBodyMethodProcessor라는 HandlerArgumentResolver의 구현체들이 처리를 하게 된다.