# Swift Closure

---

<aside>
😶‍🌫️ **클로저**

---

**코드블럭으로 C와 Objective-C의 블럭, JAVA의 람다와 비슷**

- 어떤 상수나 변수의 참조를 캡쳐해 저장
- 🌦️ 전역 함수 : 이름이 있고 어떤 값도 캡쳐하지 않는 클로저
- 💦 중첩 함수 : 이름이 있고 관련한 함수로 부터 값을 캡쳐 할 수 있는 클로저
- ☀️ 클로저 표현 : 경량화 된 문법으로 쓰이며, 관련 문맥으로부터 값을 캡쳐하는 클로저
    - *이름이 없음 → name-less*
</aside>

### 정렬 메소드 예시 🌧️

---

<aside>
💡 표준 라이브러리에 `sorted(by:)`라는 메소드의 `by`에 클로저를 넣으면 클로저대로 정렬

</aside>

```swift
let names = ["Chris", "Alex", "Ewa", "Barry", "Daniella"]
```

> 배열의 콘텐츠와 같은 타입을 갖고 두개의 인자를 갖는 클로저
`*name`의 콘텐츠는 String 타입이므로 `(String, String) -> Bool`의 타입의 클로저*
> 

```swift
// 클로저를 제공하는 일반적인 방법은 함수를 하나 만드는 것
func backward(_ s1: String, _ s2: String) -> Bool {
    return s1 > s2
}

var reversedNames = names.sorted(by: backward)
// ["Ewa", "Daniella", "Chris", "Barry", "Alex"]
```

[Closure Expressions](Swift%20Closure%206e969bbabf304058803e4dc10abef7e1/Closure%20Expressions%2017eee6e5c7514f6396f5163d4e095b97.md)

[Trailing Closures](Swift%20Closure%206e969bbabf304058803e4dc10abef7e1/Trailing%20Closures%20f182c92039914591b8c708f0425aedab.md)

[Capturing Value](Swift%20Closure%206e969bbabf304058803e4dc10abef7e1/Capturing%20Value%205483dc16279842c397241716ca867ab3.md)