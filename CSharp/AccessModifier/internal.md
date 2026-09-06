# internal
- 하나의 어셈블리 단위 내에서만 접근을 허용
    - 어셈블리 : 프로그램의 기본 단위로 빌드시 생성되는 dll이나 .exe 파일
>internal 사용법 예시
```csharp
// Project1 어셈블리 
namespace Project1
{
    internal class myProject
    {
    	public string age;
    }

    public class IsPossible
    {
    	myProject p1 = new myProject();
    }
}

// Project2 어셈블리 
namespace Project2
{
    internal class myProject2
    {
        // 다른 어셈블리에 있는 internal 클래스를 불러올 수 없음
    	myProject p1 = new myProject();
    }
}
```