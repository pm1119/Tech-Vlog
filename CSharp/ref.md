# 매개변수 한정자 ref
- 변수를 값이 아닌 참조 형식으로 전달하거나 다룰 때 사용하는 키워드.
>ref를 쓰지 않았을 경우 예시
```csharp
class Program
{
	private static void Swap(int x, int y)
	{
		int temp = x;
		x = y;
		y = temp;
	}

	private static void Main(string[] args)
	{
		c = 30; d = 40;
		Console.WriteLine($"c = {c}, d = {d}");
		Swap(c, d);
		Console.WriteLine($"c = {c}, d = {d}");
	}
}
```
- 이 코드의 경우 의도한 대로라면 c와 d의 값이 바뀌어야 하나 막상 실행해보면 그렇지 않다. 매개변수와 중괄호 내의 변수는 서로 다른 메모리 공간을 할당하기 때문이며, 값 형식은 특히나 크기가 고정되어 있기 때문이다.
- 따라서 ref 키워드를 통해 값 형식을 참조 형식으로 바꾼다면 값 대신 메모리 주소를 전달할 수 있어 매개변수와 중괄호 내 변수가 값을 공유하는 게 가능해진다.
>ref 사용법 예시
```csharp
class Program
{
	private static void Swap(ref int x, ref int y)
	{
		int temp = x;
		x = y;
		y = temp;
	}

	private static void Main(string[] args)
	{
		c = 30; d = 40;
		Console.WriteLine($"c = {c}, d = {d}");
		Swap(ref c, ref d);
		Console.WriteLine($"c = {c}, d = {d}");
	}
}
```