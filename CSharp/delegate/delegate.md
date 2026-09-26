# delegate
- 대리자라고도 불리며, 메서드를 참조하기 위해 사용한다.
- 객체를 온전히 소유하는  is a 구조나 has a 구조의 경우, 클래스에 변화가 생길 시 고유 중인 객체의 클래스에까지 변화가 일어날 위험이 있다.
- 단적으로, 플레이어는 칼을 들어야 하지만 플레이어 클래스에 변화가 생길 경우 칼에게까지 변화를 적용해서는 안 된다.
- 두 클래스 사이에 상호 작용을 유지하면서도 독립적으로 기능하게 만들어야 하는 것이다.
- 대리자(delegate)를 사용할 시 객체의 주소만 참조하는 형태이기 때문에 안전하게 상호작용을 구현할 수 있다.
- >delegate 사용법 예시
```csharp
class Player
{
	private int hp;
	private int attack;

	public delegate void AttackDelegate(int number, int damage); //대리자 생성

	public AttackDelegate OnAttack;

	public Player(int hp, int attack)
	{
		this.hp = hp;
		this.attack = attack;
	}

	public void Attack(int number)
	{
		if (OnAttack != null)
		{
			OnAttack.Invoke(number, attack); //대리자 발행
		}
	}
}

class Program
{
	private static void PlayerAttack(int number, int damage)
	{
		Console.WriteLine($"Player Attack : {number}, {damage}");
	}

	static void Main(string[] args)
	{
		Player player = new Player(100, 10);
		player.OnAttack += PlayerAttack;
	}//Main
}
```