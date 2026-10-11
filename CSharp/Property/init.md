# init
- 객체가 생성되는 시점(생성자 또는 초기화)에만 값을 할당할 수 있고, 생성된 이후에는 값을 수정할 수 없도록 만들어 불변성(Immutability)을 보장하는 접근자.
>init 예시
```csharp
public class Player
{
    public string Name { get; init; }
    public int Age { get; init; }
}

class Program
{
    static void Main()
    {
        // 1. 객체 이니셜라이저를 통한 초기화 (가능)
        var person = new Person { Name = "김철수", Age = 25 };

        // 2. 생성 이후 값 변경 시도 (불가능)
        // person.Name = "박민수"; 
    }
}
```
- 읽기 한정(get만 있음) 프로퍼티와의 차이점
    - 생성자 매개 변수를 따로 만들지 않아도 { Name = "가가가" } 같은 객체 이니셜라이저 구문을 통해 편리하게 값 초기화 가능.
