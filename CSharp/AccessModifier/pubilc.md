# public
- 객체 지향 프로그래밍의 구성 요소 중 하나인 캡슐화를 담당하는 접근 한정자 중의 하나.
- public을 사용할 경우 클래스 외부에서 스정된 필드에 접근할 수 있다는 의미다.
>public 사용법 예시
```csharp
public class TestClass
{
    public string Name = "Hello";  
}

class Program
{
    public static void Main(string[] args)
    {
        TestClass test = new TestClass();
        Console.WriteLine($"Name : {test.Name}");
    }
}
```