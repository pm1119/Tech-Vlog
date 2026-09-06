# Upcasting
- 상속이 이루어졌을 경우, 자식 클래스의 객체가 부모 클래스로 형변환하는 것.
>Upcasting 예시 
```csharp
class AA
{
    
}

class BB : AA
{

}

class Program
{
    public static void Main(string[] args)
    {
        BB bb = new BB();
        AA aa = (AA)bb;
    }
}
```