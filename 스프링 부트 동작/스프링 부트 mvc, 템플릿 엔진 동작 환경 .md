# 스프링 부트 ModelViewController(MVC), 템플릿 엔진 동작 환경
먼저 컨트롤러(HelloController)에 다음과 같은 코드를 쳐준다.

![컨트롤러(2)](%EC%82%AC%EC%A7%84%20%ED%8F%B4%EB%8D%94%5CHelloController(2).png)

먼저 @RequestParam("name")이 보인다.<br>Request = 입력받아라, Param = 매개변수, ("name") = 매개변수 이름은 name<br>라는 뜻으로 해석할 수 있다. 또 그뒤 코드를 해석해보자면<br>String name = 문자열 변수 name생성, Model model = 모델 생성 이름은 model<br>mode.addAttribute = model이라는 모델값에 속성추가,<br>("name"), name = "name"이라는 매개변수에 문자열 변수 name의 값을 넣는다.<br>return "hello-template"; = hello-template.html로 모델값과 리턴값 전달

---

templates아래에 있는 hello-template.html 검색.<br>hello-template이 있다면 모델값, 리턴값과 함께 이동

![템플릿(2)](%EC%82%AC%EC%A7%84%20%ED%8F%B4%EB%8D%94%5C%ED%85%9C%ED%94%8C%EB%A6%BF(2).png)

\+ ${name} = 모델 name 출력<br>따라서 hello 와 아까 Request받은 값을 출력.

---

한가지 예를 들자면
![로컬호스트(2)](%EC%82%AC%EC%A7%84%20%ED%8F%B4%EB%8D%94%5C%EB%A1%9C%EC%BB%AC%ED%98%B8%EC%8A%A4%ED%8A%B8(2).png)
localhost:8080/hello-mvc를 입력했을땐 오류가 걸린다.<br>이는 컨트롤러의 Request요청을 무시했기 때문인데<br>다음과 같이 고쳐주면 정상 작동한다.

---

![로컬호스트(3)](%EC%82%AC%EC%A7%84%20%ED%8F%B4%EB%8D%94%5C%EB%A1%9C%EC%BB%AC%ED%98%B8%EC%8A%A4%ED%8A%B8(3).png)
이는 Reqiest요청에 name=hello!!라고 답했기 때문에<br>name값이 hello!!가 됨과 동시에 모델값이 hello!!가 된다.

---

따라서 다음과 같이 바꾸어주면
![로컬호스트(4)](%EC%82%AC%EC%A7%84%20%ED%8F%B4%EB%8D%94%5C%EB%A1%9C%EC%BB%AC%ED%98%B8%EC%8A%A4%ED%8A%B8(4).png)
hello!!가 아닌 안녕하세요가 출력되는것을 볼수 있다.

---

## 마지막 총정리

1. 웹 브라우저 에서 localhost:8080/hello-mvc요청
2. 내장 톰캣 서버에서 해당 컨트롤러 검색 및 이동
3. HelloController의 요청에 따라 매개변수를 Request받는다
4. Request받은 값에 따라 모델값과 리턴값 뷰 리졸버(viewResolver)에게 전달
5. viewResolver가 html변환 후 웹브라우저로 리턴