# interface
- [추상 클래스](abstractclass.md)와 비슷하게 사용하는 구문.
- 다형성을 구현할 수 있는 여러 가지 방법 중 하나.
- 특징
    - 메소드, 이벤트, 인덱서, 프로퍼티만 가질 수 있음.
    - 접근 지정자 사용 불가능. 전부 public으로 정의.
    - 상속받는 클래스에게 [오버라이딩](Polymorphism.md)을 강제함.
    - 구현부가 없음.
    - 객체를 만들 수 없음.
    - 클래스는 인터페이스를 여러 개 상속받는 것이 가능함.
>interface 사용법 예시
```csharp
public interface IAA
{
    //int num; 멤버 변수를 가질 수 없다
    int num { get; set; }

    //public void Print() 접근 지정자 사용 불가능
    //void Print() {}  불가능: 함수의 정의만 가능
    void Print();
}

class AA : IAA
{
    public int num { get; set; }

    public void Print() //반드시 인터페이스의 멤버 메서드를 구현해야 함.
    {
        Console.WriteLine($"{num}");
    }
}
```