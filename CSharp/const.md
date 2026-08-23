# const
- 상수를 선언하는 키워드.
- 흔히 말하는 변수가 변하는 값이라면, 상수는 변하지 않는 값을 의미한다.
- const 키워드는 컴파일할 때 값이 결정되는 컴파일 타임의 상수로, 변하지 앟는 값인 상수이기 때문에 선언과 동시에 초기화가 되어야 한다.
>const 사용법 예시
```csharp
public class TestClass
{
    public const int MaxSize = 32; //초기화 시점에 값이 정해지며 변경 불가
}
```