# Lambda
- [대리자](../delegate.md)를 이용해 코드의 간결성과 함수형 프로그래밍의 일부를 제공하는 코드 기법
- 크게 람다식과 람다문으로 나뉜다.
- 람다의 특성
    - 1. delegate에 의해서만 정리 가능
    >Lambda 예시 1
    ```csharp
    class Program
    {
        public static void Main(string[] args)
        {
            Func<int, string> lambda = (x) => x.ToString();
        }
    }
    ```
    - 2. 정해진 타입이 존재하지 않음. 그러므로 object 타입의 어떤 멤버(4가지)도 접속 불가 
    >Lambda 예시 2
    ```csharp
    class Program
    {
        public static void Main(string[] args)
        {
            //Func<int, string> lambda2 = ((int x) => x).ToString(); 
        }
    }
    ```
    - 3. 타입이 없기에 타입을 변환하는 캐스팅도 안됨
    - 4. 람다는 delegate 형식과 반드시 일치해야 함
    >Lambda 예시 3
    ```csharp
    class Program
    {
        public static void Main(string[] args)
        {
            //Func<int, bool> lambda3 = (int x) => x; //X
    		//Func<int, bool> lambda3 = (int x) => x > 1000 == true; //O
        }
    }
    ```
    - 5. 타입이 없기에 타입 추론 형식인 var도 사용 못 함
    >Lambda 예시 4
    ```csharp
    class Program
    {
        public static void Main(string[] args)
        {
            //var v = (int x) => x; //람다식엔 타입이 없어 var이 타입을 추론할 수 없음
        }
    }
    ```
    - 6. 람다에서는 ref와 out를 사용할 수 없음
    >Lambda 예시 5
    ```csharp
    class Program
    {
        public static void Main(string[] args)
        {
            //Action<int> lamabda = (out int x) => x = 10; //X
    		//Action<int> lamabda2 = (ref int x) => x = 10; //X
        }
    }
    ```
- 람다의 종류
    - 람다식
        - 한 줄로 쓰는 형태의 람다.
        >Lambda 예시 6
        ```csharp
        class Program
        {
            public static void Main(string[] args)
            {
                Func<int, int> square = (x) => (x * x);
        		Console.WriteLine($"square = {square(5)}");
            }
        }
        ```
    - 람다문
        - 결과에 중괄호를 넣어 두 줄 이상, 즉 문으로 쓰는 형태의 람다.
        >Lambda 예시 7
        ```csharp
        class Program
        {
            public static void Main(string[] args)
            {
                Action<string> greet = name =>
		        {
			        string hello = $"Hello {name}";
			        print(hello);
		        };
		        greet("Unity");
            }
        }
        ```