# Struct
- 구조체라고도 불리며, 자신만의 사용자 지정 값 형식을 지정하기 위해 선언하는 키워드다.클래스와도 유사하나 클래스는 참조 형식이라는 차이점을 가진다.
>구조체 예시 1
```csharp
class Program
{
	public struct A
    {
		public string Name;
		public float Hp;
		public float Attack;
    }

    private static void Main(string[] args)
	{
		A a;
		a.Name = "Human";
		a.Hp = 100.0f;
		a.Attack = 50.0f;
	}
}
```
- 이런 식으로 구조체의 멤버 변수에 직접 값을 초기화해 사용할 수 있다.
>구조체 예시 2
```csharp
class Program
{
	public struct A
    {
		public string Name;
		public float Hp;
		public float Attack;

		public void Print()
		{
			Console.WriteLine($"이름: {Name}");
			Console.WriteLine($"체력: {Hp}");
			Console.WriteLine($"공격력: {Attack}");
		}
    }

    private static void Main(string[] args)
	{
		A a;
		a.Name = "Human";
		a.Hp = 100.0f;
		a.Attack = 50.0f;
		a.Print();
	}
}
```
클래스와 사용 방법은 유사하므로 구조체 안에 함수를 넣는 것도 가능하다.