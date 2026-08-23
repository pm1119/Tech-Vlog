# 매개변수 한정자 out
- 함수의 리턴과 비슷한 역할을 하는 키워드.
- ref 키워드와 마찬가지로 값을 참조로 변화시켜준다.
- ref 키워드와의 차이점은 ref 키워드는 초기화를 생략할 수 잆는 것과 달리 out은 초기화를 생략하는 것이 가능하다. 하지만 반드시 함수 내부에서 값을 세팅해주어야 한다.
>out 사용법 예시
```csharp
class Program
{
	private static void TestOut(out int val1, out int val2)
	{
		val1 = 10;
		val2 = 20;
	}

	private static void Main(string[] args)
	{
		int c = 5, d;
		TestOut(out c, out d);
		Console.WriteLine($"c = {c}, d = {d}");
	}
}
```