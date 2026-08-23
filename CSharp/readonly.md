# readonly
- 상수를 선언하는 키워드.
- 흔히 말하는 변수가 변하는 값이라면, 상수는 변하지 않는 값을 의미한다.
- readonly는 런타임 상수로, 한번 초기화한 후에는 변하지 않으나 프로그램이 실행 중에 초기화하는 것도 가능하다. 즉, 클래스 생성자에서만 값을 초기화해줄 수 있다.
>readonly 사용법 예시
```csharp
public class TestClass
{
    public readonly int a;  
    public readonly int b = 20;  
    public TestClass()  
    {    
        a = 99;   // 생성자 내부에서 초기화 가능    
        b = 33;  
    }
}
```