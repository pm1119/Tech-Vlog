# delegate - Predicate
- 대리자의 일종으로, [Func](Func.md)와 같이 리턴을 반환하는 대리자이지만, bool 형식만 리턴할 수 있다.
- 또한 Func가 파라미터를 여러 개 사용할 수 있는 것과 달리 Predicate는 하나만 사용할 수 있다.
>Predicate 예시
```csharp
class Program
{
	public static void Main(string[] args)
	{
		Predicate<string> predicate = (str) => str.Length > 5;
		bool result = predicate("Hello Lambda");
		Console.WriteLine($"Case5 : {result}");
	}
}
```