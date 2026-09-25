# is
- C#에서 == 연산자와 비슷한 기능으로 쓰이는 키워드
- A는 B이다는 영어 문법 그대로 특정 형식과 호환되는지 아닌지 확인하거나 패턴을 일치시켜 true 혹은 false를 반환한다.
- is 연산자를 이용하면 부모 클래스를 자식 클래스에 대입하는 [다운캐스팅](Casting/Downcasting.md)을 할 수 있다.
>is 예시 
```csharp
class Program
{
    public static void Main(string[] args)
    {
        int a = 10;
        if(a is int)
        {
            Console.WriteLine("a는 int");
        }
    }
}
```