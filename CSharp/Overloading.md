# Overloading
- 객체 지향 프로그래밍의 다섯 가지 요소 중 [다형성](Polymorphism/Polymorphism.md)에 해당하는 요소 중 하나.
- 상속이 클래스간 공통된 요소를 부모 클래스로 묶는 것이라면, 오버로딩은 함수의 이름을 중복 사용하는 것이다.
>파라미터의 개수에 따른 오버로딩
```csharp
class Program
{
	public void Print()
	{

	}

	public void Print(int value)
	{

	}
}
```
- 함수의 오버로딩은 파라미터의 개수나 자료형에 따라 결정되며, 원칙적으로는 함수의 이름을 중복 사용하는 것이 불가능하나 위의 사례처럼 파라미터의 개수가 다른 경우 다른 함수로 인정되어 중복 사용이 가능해진다.
>파라미터의 자료형에 따른 오버로딩
```csharp
class Program
{
	public void Print(string text)
	{

	}

	public void Print(int value)
	{

	}
}
```
- 마찬가지로 파라미터의 개수가 같더라도 자료형이 다를 경우 오버로딩이 가능하여 중복 사용이 가능해진다.
- 오버로딩을 통해 비슷한 기능을 일일이 함수를 따로 만들 필요 없이 하나의 이름을 중복 사용할 수 있게 되어 객체 지향 프로그래밍의 핵심인 유지보수 편의성을 위한 설계의 효율화가 가능해진다.