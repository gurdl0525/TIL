# Trailing Closures

---

<aside>
🌈 **후위 클로저**

---

**함수의 마지막 인자로 클로저를 넣고 그 클로저가 길다면 후위 클로저를 사용**

```swift
func someFunctionClosure(closure: () -> Void) {
    // function body goes here
}
```

*이런 형태의 함수와 클로저가 있다면*

```swift
// 위 클로저의 인자 값 입력 부분과 반환 형 부분을 생략해 다음과 같이 표현
someFunctionClosure(closure: {
    // closure's body goes here
})
```

```swift
//후위 클로저로 표현하면 아래와 같이 표현
someFunctionClosure() {
    // trailing closure's body goes here
}
```

</aside>

```swift
// 정렬 예제를 후위 클로저를 이용해 표현
reversedNames = names.sorted() { $0 > $1 }
```

만약 함수의 마지막 인자가 클로저이고 후위 클로저를 사용하면 괄호 생략

```swift
reversedNames = names.sorted { $0 > $1 }
```