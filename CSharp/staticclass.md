# static class
- 정적 키워드인 [static](static.md)을 사용한 정적 클래스
- 정적 클래스는 new 키워드를 사용해서 객체를 만들 수 없으며 그렇기에 생성자를 포함할 수 없음.
- 정적 클래스의 모든 멤버는 static을 붙여 정적으로 설정해줘야 함.
- 객체들이 처음 호출될 때 생성되고 프로그램이 종료될 때 해제되기 때문에 정적 클래스는 어디서든 접근할 수 있음.
>static class 사용법 예시
```csharp
public static class Calculator
{
    public static int Plus (int a, int b)
    {
        return a + b;
    }

    public static int Minus (int a, int b)
    {
        return a - b;
    }
}

public class Program
{
    static void Main (string[] args)
    {
        int addResult = Calculator.Plus (5, 3);
        int minusResult = Calculator.Minus (5, 3);

        Console.WriteLine (addResult);
        Console.WriteLine (minusResult);
    }
}
```