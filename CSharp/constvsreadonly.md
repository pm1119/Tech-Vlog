# const vs readonly
- [const](const.md)
    - const 키워드는 컴파일할 때 값이 결정되는 컴파일 타임의 상수로, 변하지 앟는 값인 상수이기 때문에 선언과 동시에 초기화가 되어야 한다.
    - 즉, 정적(static) 변수와 동일하게 취급하기 때문에 (클래스).(상수)로 접근해야 함.
- [readonly](readonly.md)
    - readonly는 런타임 상수로, 한번 초기화한 후에는 변하지 않으나 프로그램이 실행 중에 초기화하는 것도 가능하다. 즉, 클래스 생성자에서만 값을 초기화해줄 수 있다.
    - 그러므로 const로 선언한 상수와는 달리 readonly로 선언한 상수는 (객체).(상수)로 접근해야 한다.
>const vs readonly 예시
```csharp
public class TestClass()  
{    
    public const int Number1 = 10;  
    public readonly int Number2; 

    public TestClass(int num)
    {
        b = num;
    }
}

class Program
{ 
    public static void Main(string[] args)
    {
        TestClass test = new TestClass(50);
        Console.WriteLine($"Student.JobName : {TestClass.Number1}");
        Console.WriteLine($"stu.StudentName : {test.Number2}");
    }
}
```