# Reflection
- 애플리케이션 실행 중 어셈블리(메서드, 프로퍼티, 생성자 등 인스턴스의 데이터 타입 정보)의 내용을 확인하거나 검사하려는 경우 사용되는 기능.
- 테스트 및 디버그 용도로 주로 사용되며, 애플리케이션을 개발할 때, 디버깅 또는 런타임에 알 수 없는 객체의 동작을 분석하기 위해 사용하거나 외부 라이브러리에 존재하는 클래스 및 메서드를 분석하는 용도로 사용한다.
- 타입 정보를 가져오는 원리
    - GetType() 메서드
        - C#의 모든 데이터 타입은 Object 클래스로부터 비롯된다. 따라서 모든 데이터 타입은 Object 클래스에 존재하는 ToString(), Equals(), GetType(), GetHashCode(), ReferenceEquals() 메서드를 사용할 수 있다.
        - 이 중 GetType() 메서드는 Type이라는 모든 데이터 타입의 정보를 담고 있는 클래스를 반환해 타입 정보를 가져온다.
        >GetType() 메서드 예시
        ```csharp
        class Program
        {
          static void Main(string[] args)
          {
            int num = 10;
            Type type1 = num.GetType();
            Console.WriteLine(type1.Name);
            Console.WriteLine(type1.Namespace + "\n");

            bool boolValue = false;
            Type type2 = boolValue.GetType();
            Console.WriteLine(type2.Name);
            Console.WriteLine(type2.Namespace + "\n");

            string strValue = "Hello";
            Type type3 = strValue.GetType();
            Console.WriteLine(type3.Name);
            Console.WriteLine(type3.Namespace + "\n");

            ArrayList al = new ArrayList();
            Type type4 = al.GetType();
            Console.WriteLine(type4.Name);
            Console.WriteLine(type4.Namespace);
          }
        }
        ```
    - typeof 키워드와 Type 클래스의 GetType() 메서드
        - 그러나 GetType() 메서드는 반드시 객체의 인스턴스가 존재해야 호출할 수 있다는 번거로운 단점이 있다.
        - 이에 따라 매개변수로 데이터 타입을 전달하는 방식의 typeof와 Type 클래스의 객체를 직접 생성해 GetType() 메서드를 쓸 수도 있다.
        >typeof와 Type 클래스 사용 예시
        ```csharp
        class Program
        {
          static void Main(string[] args)
          {
            Type type2 = typeof(ArrayList);
            Console.WriteLine(type2.Name);

            Type type3 = Type.GetType("System.Collections.ArrayList");
            Console.WriteLine(type3.Name);
          }
        }
        ```