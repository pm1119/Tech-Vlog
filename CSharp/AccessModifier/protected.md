# protected
- 객체 지향 프로그래밍의 구성 요소 중 하나인 캡슐화를 담당하는 접근 한정자 중의 하나.
- 클래스의 상속과 밀접한 연관을 가지는 키워드로, 부모 클래스로부터 상속을 받은 자식 클래스는 부모의 기능을 물려받아 사용할 수 있으나, 부모 클래스의 변수가 private인 경우 모든 외부 접근을 차단하는 private 키워드이 특성상 자식 클래스에도 예외가 될 수 없다. 
- 하지만 public으로 무작정 전환할 수도 없는 노릇이므로, 이에 대한 절충안으로 나타난 키워드가 바로 protected다. private에서 보안 강도를 한 단계 낮춰 자식 클래스에서 부모 클래스의 변수를 공유받을 수 있도록 하는 것이다. 
>protected 사용법 예시
```csharp
class Player
{
    protected string name;  
    protected int hp;

    public Player(string name, int hp)
    {
	    this.name = name;
	    this.hp = hp;
    }

    protected void Print()
    {
	    Console.WriteLine($"Name : {name}, HP : {hp}");
    }
}

class Warrior : Player
{
	public Warrior(string name, int hp) : base(name, hp)
	{
		Console.WriteLine("전사 선택");

		Print();
	}
}

class Program
{
    public static void Main(string[] args)
    {
        Warrior warrior = new Warrior("Bob", 100);
    }
}
```