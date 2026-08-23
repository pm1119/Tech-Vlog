# 매개변수 한정자 in
- ref, out과 마찬가지로 변수를 값이 아닌 참조 형식으로 전달하거나 다룰 때 사용하는 키워드.
- 함수 내부에서 값을 변경할 수 없으므로, 반드시 초기화를 해주어야 한다.
- 구조체(struct)와 같이 데이터가 클 경우 구조체 내부의 모든 데이터를 복사하는 과정을 생략하고
구조체 객체의 참조를 전달하는 과정으로 효율성을 높일 수 있다.
>in 사용법 예시
```csharp
public class TestClass
{
    int a;

    public void Test(in int data)
    {
        a = data; // 가능
        Console.WriteLine(data); // 가능
        
        data = 3; // 불가능 , 컴파일 에러
    }
}
```