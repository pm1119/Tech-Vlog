# Auto-Implemented Property
- [프로퍼티](Property.md)를 사용하면 객체지향 프로그래밍의 요소 중 하나인 은닉성을 좀 더 간결하고 간단하게 구현할 수 있다.
- 하지만 자동 구현 프로퍼티를 사용하면 이를 더 간결하게 구현할 수 있다.
>Auto-Implemented Property 예시
```csharp
class MyClass
{
    public string Name{ get; set;}
}

class MyClass2
{
    public string Name{ get; private set;}
}
```
- 클래스의 기본 생성자 원리와 비슷하게 컴파일러가 자동으로 private 필드를 생성해주는 것이다.
- 단, 기본적인 get과 set만 입력할 수 있으며 클래스에 따로 생성자를 구현할 경우 기본 생성자가 사라지듯이 사용자 지정 코드를 작성할 경우 사용할 수 없다. 