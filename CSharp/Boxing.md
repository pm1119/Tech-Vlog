# Boxing
- 값 형식을 참조 형식으로 변환하는 것.
- 최적화에 주로 쓰이나, 너무 최적화에만 집중한 코드는 유연성이 떨어지기 때문에 최소한의 사용이 권장된다.
- object 키워드가 주로 쓰이며, 그 이유는 object가 C#의 모든 타입을 하나의 통일된 형식 시스템으로 다룰 수 있는 키워드이기 때문이다.
>박싱 예시
```csharp
class Program
{
	private static void Main(string[] args)
	{
		int number;
		object thing;

		number = 42;

		//Boxing
		thing = number;

		//UnBoxing
		number = (int)thing;
	}
}
```