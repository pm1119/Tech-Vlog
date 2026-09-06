# static
- 변수 또는 함수, 클래스에 정적 속성을 부여해주는 키워드.
- static 키워드가 붙으면 클래스로부터 객체를 생성하지 않고도 호출해줄 수 있다.
>static 사용법 예시
```csharp
class Knight
{

    // 필드
    static public int counter = 1; //knight라는 객체에 단 하나만 존재하므로 객체를 몇 번이고 생성하든 공유함

    public int id;
    public int hp;
    public int attack;

    //메소드
    static public Knight CreateKnight()
    {
        Knight knight = new Knight();
        return knight;
    }

    public Knight()
    {
        id = counter;
        counter++;

        hp = 100;
        attack = 10;
        Console.WriteLine("기사 생성자 호출!");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Knight knight = new Knight();

        Knight knight2 = Knight.CreateKnight(); // static을 통해 knight2라는 객체를 새로 생성하지 않고도 호출 가능
    }
}
```
- 단, static이 아닌 것은 접근이 불가하며 정적 함수는 정적 변수만 사용 가능
>static 사용법 예시 2
```csharp
class AA
{
    public int num;
    public static int sNum;
    public static int instanceNum;

    public AA()
    {
        ++instanceNum;

        WriteLine($"instanceNum: {instanceNum}");
    }

    public void AddStaticNum()
    {
        ++sNum;
    }

    public void Print()
    {
        WriteLine($"num: {num}");
        WriteLine($"sNum: {sNum}");
    }

    //static 함수(정적 함수)는 반드시 정적 변수만 사용 가능
    public static void StaticPrint()
    {
        //Console.WriteLine($"num: {num}"); 정적 변수가 아니므로 불가능
        Console.WriteLine($"StaticPrint sNum: {sNum}");
        Console.WriteLine($"StaticPrint instanceNum: {instanceNum}");
    }
}
```