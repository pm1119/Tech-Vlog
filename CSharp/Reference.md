# Reference
- 동적 할당(참조 형식)
    - 크기는 가변형.
    - 변수에 new 키워드를 붙여 만들어짐.
    - 힙 영역에 클래스 구역이 저장되어 위치한 주소를 스택 영역에 위치한 변수가 참조하여 할당함.
    - 실행 상태(런타임) 단계에서 결정.
>참조 형식 예시
```csharp
class Program
{
	class A
    {

    }

    private static void Main(string[] args)
	{
		A ob = new A();
	}
}
```