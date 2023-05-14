# Property Observers

---

![Untitled](Property%20Observers%203de9804952ec4e85b282851d086b1cb8/Untitled.png)

<aside>
<img src="Property%20Observers%203de9804952ec4e85b282851d086b1cb8/Untitled%201.png" alt="Property%20Observers%203de9804952ec4e85b282851d086b1cb8/Untitled%201.png" width="40px" /> **프로퍼티 옵저버**

---

**프로퍼티에 새 값이 set 될 때마다 이 이벤트를 감지할 수 있는 옵저버**

- 새 값이 이전 값과 같더라도 항상 호출
- 지연 저장 프로퍼티에서 사용 **X**
- 계산된 프로퍼티는 setter가 있기 때문에 따로 옵저버를 정의할 필요 **X**
- 🐠 willSet : 값이 저장되기 바로 직전에 호출 되는 프로퍼티
- 🍣 didSet : 값이 저장되고 직후에 호출 되는 프로퍼티

> 서브클래스에는 initializer가 호출 된 후 프로퍼티 옵저버 실행
> 
</aside>

```swift
class StepCounter {
    var totalSteps: Int = 0 {
        willSet(newTotalSteps) {
            print("About to set totalSteps to \(newTotalSteps)")
        }
        didSet {
            if totalSteps > oldValue  {
                print("Added \(totalSteps - oldValue) steps")
            }
        }
    }
}
let stepCounter = StepCounter()
stepCounter.totalSteps = 200
// About to set totalSteps to 200
// Added 200 steps
stepCounter.totalSteps = 360
// About to set totalSteps to 360
// Added 160 steps
stepCounter.totalSteps = 896
// About to set totalSteps to 896
// Added 536 steps
```