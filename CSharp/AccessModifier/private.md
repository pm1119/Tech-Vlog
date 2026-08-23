# private
- 객체 지향 프로그래밍의 구성 요소 중 하나인 캡슐화를 담당하는 접근 한정자 중의 하나.
- public이 클래스 외부 접근을 용인하게 하는 키워드라면 private은 반대로 모든 외부 접근을 차단하는 키워드로, 외부에서 수정하지 못하게 해야 할 때 사용한다.
>private 사용법 예시
```csharp
public class TestClass
{
    private string name;  
}

class Program
{
    public static void Main(string[] args)
    {
        TestClass test = new TestClass();
        //Console.WriteLine($"Name : {test.name}"); //private 키워드로 인해 외부 접근이 차단되었기 때문에 불가능
    }
}
```