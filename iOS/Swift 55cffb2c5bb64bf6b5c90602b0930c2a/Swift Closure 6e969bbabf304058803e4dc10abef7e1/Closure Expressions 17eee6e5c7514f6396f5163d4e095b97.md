# Closure Expressions

---

<aside>
🕯️ **클로저 표현**

---

**코드의 명확성과 의도를 잃지 않으면서 문법을 축약해 사용할 수 있는 최적화 방법을 제공**

- 클로저를 명확하게 표현하는 방법으로 문법에 초첨이 맞춰져 있음
- Swift에서 클로저 표현은 최적화 됨, 최적화는 다음과 같은 내용을 포함
    1. 문맥에서 인자 타입과 반환 타입의 추론
    2. 단일 표현 클로저에서의 암시적 반환
    3. 축약된 인자 이름
    4. 후위 클로저 문법
</aside>

## Syntax 📝

---

```swift
// 클로저 표현 문법의 일반적 형태
{ (parameters) -> return type in
    statements
}
```

```swift
//ex
reversedNames = names.sorted(by: { (s1: String, s2: String) -> Bool in
    return s1 > s2
})
```

<aside>
🔥 **문맥에서의 타입 추론**

---

**이미 (String, String) -> Bool 타입의 인자가 들어와야 하는지 알기 때문에 생략 O**

```swift
reversedNames = names.sorted(by: { s1, s2 in return s1 > s2 } )
```

</aside>

<aside>
🌚 **단일 표현 클로저에서의 암시적 반환**

---

**단일 표현 클로저에서는 반환 키워드를 생략**

```swift
reversedNames = names.sorted(by: { s1, s2 in s1 > s2 } )
```

</aside>

<aside>
🏷️ **인자 이름 축약**

---

**자동으로 축약 인자 이름 제공 → 인자 값을 순서대로 $0, $1, $2 등으로 사용**

```swift
reversedNames = names.sorted(by: { $0 > $1 } )
```

</aside>

<aside>
🌩️ **연산자 메소드**

---

**Swift의 String타입 연산자에는 비교 연산자가 구현해 되어있음**

```swift
reversedNames = names.sorted(by: >)
```

</aside>