# virtual(가상화)
- 몸체가 있는 부모 함수를 자식 클래스에서 필요에 따라 재정의(override)하는 것. virtual 키워드를 사용한다.
- 동적 할당에서만 가능.
>virtual 사용법 예시
```csharp
public class A
{
    public string Name = "Hello";  

    pubilc virtual void Print()
    {
        Console.WriteLine($"{Name}");
    }
}

public class B : A
{
    pubilc override void Print()
    {
        base.Print();
    }
}

class Program
{
    public static void Main(string[] args)
    {
        B b = new B();
        b.Print();
    }
}
```