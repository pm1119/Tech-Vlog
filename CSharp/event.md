# event
- [대리자(delegate)](delegate.md)의 일종으로, 특수한 제약조건이 추가된 대리자(delegate)를 뜻한다.
- 조건
    - 추가(+=) 및 제거(-=)만 가능하다. 
    - 클래스 외부에서 직접 호출 불가능.
>event 사용법 예시
```csharp
public class MyButton
{
    // 1. event 선언
    public event EventHandler Click;

    public void MouseButtonDown()
    {
        if (this.Click != null)
        {
            // 5. 이벤트 발생
            Click(this, EventArgs.Empty);
        }
    }
}

class Program
{
    public static void Main(string[] args)
    {
        var button = new MyButton();

        // 3. eventhandler에 이벤트 추가
        button.Click += new EventHandler(BtnClick);

        // 4. 이벤트 발생을 위한 함수 호출
        button.MouseButtonDown();
    }

    // 2. eventhandler에 추가할 형식에 맞는 event 함수 선언
    static void BtnClick(object sender, EventArgs e)
    {
        Console.WriteLine("button clicked!");
    }
}
```