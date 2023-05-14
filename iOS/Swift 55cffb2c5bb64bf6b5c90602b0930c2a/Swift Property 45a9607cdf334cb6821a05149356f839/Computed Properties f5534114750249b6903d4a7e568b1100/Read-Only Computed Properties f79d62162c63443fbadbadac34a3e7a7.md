# Read-Only Computed Properties

---

<aside>
🥙 **읽기전용 계산된 프로퍼티**

---

**getter만 있고 setter를 제공하지 않는 계산된 프로퍼티를 읽기전용 계산된 프로퍼티**

```swift
//volume이라는 읽기전용 계산된 프로퍼티를 사용한(예)
struct Cuboid {
    var width = 0.0, height = 0.0, depth = 0.0
    var volume: Double {
        return width * height * depth
    }
}
let fourByFiveByTwo = Cuboid(width: 4.0, height: 5.0, depth: 2.0)
print("the volume of fourByFiveByTwo is \(fourByFiveByTwo.volume)")
// "the volume of fourByFiveByTwo is 40.0" 출력
```

</aside>

> 읽기전용 계산된 프로퍼티를 포함해 계산된 프로퍼티를 선언시에는 반드시 let이 아니라 var로 선언
계산된 프로퍼티는 읽기전용이라 하더라도 계산 값에 따라 값이 변할 수 있기 때문에 var로 선언
>