# delegate - Action
- 대리자의 일종으로, 우리가 흔히 쓰는 void 함수와 같이 리턴이 없는 함수 격으로 쓰인다.
- 제네릭을 통해 타입을 결정하면 그 타입이 파라미터가 된다.
- 물론 제네릭 없이 쓰는 것도 가능하다.
>Action 예시
```csharp
class Program
{
	public void Test(int a, string b)
	{
		Console.WriteLine($"Test : {a}, {b}");
	}

	public static void Main(string[] args)
	{
		Action<int, string> action;
		action = Test;
		action(10, "Unity");
	}
}
```