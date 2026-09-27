# set
- [프로퍼티](Property.md)의 기능 중 읽기를 담당하는 기능.
- 읽기만 하는 [get](get.md)과는 반대로 외부의 값을 할당할 수 있는 기능이다.
>set 예시
```csharp
public class Player
{
	private int hp;

	public int Hp 
	{
		get
		{
			return hp;
		}
		set
		{
			 hp = value;
		}
	}

	public int Attack { get; set; }

	public int Address { get; private set; } //set에 private이 붙을 경우 읽기 전용이 된다.
}

class Program
{
	public static void Main(string[] args)
	{
		Player player = new Player()
		{
			Hp = 100,
			Attack = 50
		};

		Console.WriteLine($"Player.Hp: {player.Hp}");
        Console.WriteLine($"Player.Attack: {player.Attack}");
	}
}
```