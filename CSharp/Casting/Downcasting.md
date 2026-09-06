# Downcasting
- 상속이 이루어졌을 경우, 부모 클래스의 객체가 자식 클래스로 형변환하는 것.
>Downcasting 예시 
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
        AA aa = new AA();
        BB bb = (BB)aa;
    }
}
```