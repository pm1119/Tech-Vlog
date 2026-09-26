# event
- [대리자(delegate)](delegate.md)의 일종으로, 특수한 제약조건이 추가된 대리자(delegate)를 뜻한다.
- 조건
    - 추가(+=) 및 제거(-=)만 가능하다. 
    - 클래스 외부에서 직접 호출 불가능.
>event 사용법 예시 1
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
- 또한 이벤트를 비롯한 대리자에는 발행/구독이란 개념이 있어 굳이 이벤트를 따로 선언할 필요 없이 객체를 통해 상호작용을 할 수 있다.
- 이 경우, Invoke 함수를 이용해 발행할 수 있으며, 반드시 이벤트의 파라미터가 동일한 함수여야만 호환이 된다.
>event 사용법 예시 2
```csharp
public class Player
{
    public int MaxHp;
    public int CurrentHp;

    public event Action<int, int> OnHpChanged;

    public Player(int hp)
    {
        MaxHp = hp;
        CurrentHp = MaxHp;
    }

    public void Damaged(int damage)
    {
        CurrentHp = CurrentHp - damage;
        OnHpChanged?.Invoke(CurrentHp, MaxHp);
    }
}

class Program
{
    public static void Main(string[] args)
    {
        Player player = new Player(100);
        player.OnHpChanged += HpView; //동일한 타입 및 개수의 파라미터여야만 가능
    }

    public void HpView(int currentHp, int maxHp)
    {
        Console.WriteLine($"현재 체력 : {currentHp, maxHp}")
    }
}
```