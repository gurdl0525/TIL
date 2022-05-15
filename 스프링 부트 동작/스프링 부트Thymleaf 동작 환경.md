# 스프링 부트  Thymleaf 동작환경
먼저 아래와 같은 <span style="color:#fff5b1"> 컨트롤러</span>가 있다고 가정해보자. &nbsp; (이름 : HelloController)
```
package hello.hellospring.controller;


import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HelloController {

    @GetMapping("hello")
    public String hello(Model model){
        model.addAttribute("data","spring!!");
        
        return "hello";
    }
}
```

다음 웹브라우저가 localhost:8080/hello를 <span style="color:#fff5b1">내장 톰캣서버</span>에 보낸다.<br>그러면 hello에 대한 컨트롤러(HelloController)로 이동한다.

---

해당 컨트롤러가 동작하게 된다.<br>아래 코드에서 data라는 모델값이 있고, 리턴값( return "hello"; )이 있다.
```
@Controller
public class HelloController {

    @GetMapping("hello")
    public String hello(Model model){
        model.addAttribute("data","spring!!");
        
        return "hello";
    }
}
```
리턴값에 따라 값을 반환한다. (이때 모델값도 같이 이동한다)

---

따라서 리턴값에 의해 hello.html을 찾아야하는데<br>스프링 부트는 html을 찾을때
<span style="color:#fff5b1">템플릿 아래에서 찾는다</span>.

![템플릿](%ED%85%9C%ED%94%8C%EB%A6%BF.png)

따라서 템플릿 폴더 안에 있는 hello.html을 찾는다.

---

그렇다면 hello.html을 드여다 보자. 아래와 같은 코드가 구성되어있다.<br>보면 \<p> \</p>안에 + ${data} 가 보인다.
```
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요. ' + ${data}" > </p>
</body>
</html>
```
이뜻은 아까 HelloController에서 만든 모델(data)를 의미한다.

---
 
data의 실제값은 spring!!으로 지정해 주었기 때문에, 실제 출력 결과를 보면

![로컬 호스트](%EB%A1%9C%EC%BB%AC%20%ED%98%B8%EC%8A%A4%ED%8A%B8.png)


data대신 <span style="color:#fff5b1">data의 실제값(spring!!)이 출력</span>된다. 이와같은 html을 변환시켜주는걸 viewResolver가 하게된다.<br>
컨트롤러(HelloController)가 리턴값으로 문자를 반환하면<br><span style="color:#fff5b1">뷰 리졸버(viewResolver)가 화면을 찾아 처리(렌더링)</span>해서 웹브라우저로 보내준다.

---

## 마지막으로 정리

![예시사진 1](%EC%98%88%EC%8B%9C%EC%82%AC%EC%A7%84%20(1).png)

1. 웹브라우저가 로컬호스트8080/hello를 보낸다<br>
2. 내장 톰켓 서버를 거쳐서 해당 컨트롤러가 있는지 확인<br>
3. 만약 있다면 해당 컨트롤러로 이동<br>
4. 컨트롤러 안에있던 모델(data)값과 리턴(return "hello";)값을 뷰 리졸버(viewResoler)한테 전달<br>
5. 뷰 리졸버가 html을 변환 시킨후에 다시 웹브라우저로 보내 비로소 우리가 보는 화면이 된다

---