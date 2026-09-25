# as
- 객체를 안전하게 [캐스팅](Casting/Casting.md)하기 위해 사용하는 키워드. 
- 변환이 실패할 경우 null을 반환한다.
>as 예시 
```csharp
class Character
{

}

class Player : Character
{
    public Player(string name, int hp, int attack)
    {
        
    }
}

class Monster : Character
{
    public Monster(string name, int hp, int attack)
    {
        
    }
}

class Program
{
    public static void Main(string[] args)
    {
        Player player1 = new Player("Player", 100, 20);
        Console.WriteLine($"player1 -> Character : {player1 is Character}"); //True
		Console.WriteLine($"character -> Player : {character is Player}"); //True

		Monster monster = new Monster("Monster", 100, 10);
		Console.WriteLine($"monster -> Character : {monster is Character}"); //True
		Console.WriteLine($"character -> Monster : {character is Monster}"); //False
    }
}
```