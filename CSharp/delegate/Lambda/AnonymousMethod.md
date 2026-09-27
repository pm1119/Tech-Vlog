# Anonymous Method
- 익명 메서드라고 불리며, 말 그대로 이름이 없는 함수를 뜻한다. [람다](Lambda.md)의 근원이 되는 기법이라 할 수 있다.
- 별도의 반환 타입이나 정의 없이 delegate를 이용해 즉석에서 작성한다.
>보통의 메서드 선언 예시
```csharp
class Program
{
    public static void Main(string[] args)
    {
        Print("Hello World!");
    }

    public void Print(string text)
    {
        Console.Write(text);
    }
}
```
>익명 메서드 선언 예시
```csharp
class Program
{
    public static void Main(string[] args)
    {
        Func<int, int> square = (x) => (x * x);
		Console.WriteLine($"square = {square(5)}");
    }
}
```
- 이렇게 익명 메서드를 사용하는 것으로 코드의 양을 줄일 수 있다.