# get
- [프로퍼티](Property.md)의 기능 중 읽기를 담당하는 기능.
- 말 그대로 외부에서 값을 읽어들이는 기능이다. 
- 하지만 읽기만 가능하므로 외부에서 값을 변경할 수는 없다.
>get 예시
```csharp
public class Player
{
	private int hp = 100;
	public int Hp { get => power; }

	//public int Hp => hp; //get만 사용할 때는 get을 생략하고 람다식처럼 사용하는 것도 가능하다.
}

class Program
{
	public static void Main(string[] args)
	{
		Player player = new Player();
		Console.WriteLine($"Hp : {player.Hp}");
	}
}
```