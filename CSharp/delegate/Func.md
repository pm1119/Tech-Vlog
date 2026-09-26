# delegate - Func
- 대리자의 일종으로, [Action](Action.md)과 비슷하지만 Func는 리턴이 존재한다.
- 따라서 제네릭을 하지 않아도 쓸 수 있는 Action과 달리 Func는 반드시 제네릭을 통해 리턴 타입을 결정해줘야 한다.
>Func 예시
```csharp
class Program
{
	public int Test(int a)
	{
		return a;
	}

	public static void Main(string[] args)
	{
		Func<int, int> func;
		func = Test;
		Console.WriteLine(func(10));
	}
}
```