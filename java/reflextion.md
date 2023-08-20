리플렉션
===
 파일을 업로드 하는 기능안에 썸네일로 변환하고 저장하는 프라이빗 메소드를 테스트하고 싶은 상황이 생겼다.

```
        File file = new File("src/test/resources/test.jpg");
        Method makeThumbnailFromGifMethod = ResourceServiceImpl.class.getDeclaredMethod("convertToPng", File.class);
        makeThumbnailFromGifMethod.setAccessible(true);
        File result = (File) makeThumbnailFromGifMethod.invoke(resourceService, file);
```
ResourceServiceImpl클래스에서 getDeclaredMethod를 통해 메소드이름과 파라미터 인자를 통해 메소드를 가져왔다.

메소드 인자로 클래스를 받을 수 있었는데 프라이빗 메소드에서 프리미티브타입을 받으면 래퍼클래스 형식으로 받도록 수정해야 했다