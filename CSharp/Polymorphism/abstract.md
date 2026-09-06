# abstract(추상화)
- 몸체가 없는 부모 함수를 자식 클래스에서 무조건 자식 클래스에서 재정의(override)하는 것. abstract 키워드를 사용한다.
- 마찬가지로 동적 할당에서만 가능.
- 추상 메서드를 포함한 클래스를 [추상 클래스](abstractclass.md)라 부른다.
>abstract 사용법 예시
```csharp
public abstract class A //추상 메서드를 포함한 클래스는 추상 클래스가 되어야 함
{
    public string Name = "Hello";  

    pubilc abstract void Print();
}

public class B : A
{
    pubilc override void Print()
    {
        Console.WriteLine($"{Name}");
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