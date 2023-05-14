# Stored Properties

---

<aside>
💡 **저장 프로퍼티**

`let`키워드를 이용해서 상수 혹은 `var`키워드를 이용해서 변수로 선언

```swift
struct FixedLengthRange {
    var firstValue: Int
    let length: Int
}
var rangeOfThreeItems = FixedLengthRange(firstValue: 0, length: 3)
// 범위 값은 0, 1, 2 입니다.
rangeOfThreeItems.firstValue = 6
// 범위 값은 6, 7, 8 입니다.
```

> **상수 구조체 인스턴스의 저장 프로퍼티 🎯**
> 
> 
> ---
> 
> **구조체를 상수로 선언하면(`let`) 그 구조체 인스턴스의 프로퍼티는 변경 X**
> 
> ```swift
> let rangeOfFourItems = FixedLengthRange(firstValue: 0, length: 4)
> // 범위 값은 0, 1, 2, 3 입니다.
> rangeOfFourItems.firstValue = 6
> // 에러 발생!
> ```
> 
</aside>

<aside>
🦥 **Lazy Stored Properties**

---

**값이 처음으로 사용 되기 전에는 계산되지 않는 프로퍼티**

- 프로퍼티의 선언 앞에 `lazy`키워드
- 반드시 변수(`var`)로 선언해야 함
    - → 상수는 초기화가 되기전에 항상 값을 같는 프로퍼티
- *~~지연 프로퍼티가 여러 스레드에서 사용될 때 지연 프로퍼티가 한번만 실행되는 걸 보장하지 않음~~*

```swift
class DataImporter {
    /*
        DataImporter는 외부 파일에서 데이터를 가져오는 클래스입니다.
         이 클래스는 초기화 하는데 매우 많은 시간이 소요된다고 가정하겠습니다.
     */
    var filename = "data.txt"
    // 데이터를 가져오는 기능의 구현이 이 부분에 구현돼 있다고 가정
}

class DataManager {
    lazy var importer = DataImporter()
    var data = [String]()
    // 데이터를 관리하는 기능이 이 부분에 구현돼 있다고 가정
}

let manager = DataManager()
manager.data.append("Some data")
manager.data.append("Some more data")
// DataImporter 인스턴스는 이 시점에 생성돼 있지 않습니다.
```

```swift
print(manager.importer.filename)
// the DataImporter 인스턴스가 생성되었습니다.
// "data.txt" 파일을 출력합니다.
```

> `manager.importer.filename`가 실행돼 실제 프로퍼티에 처음 접근할 때 인스턴스 생성
> 
</aside>