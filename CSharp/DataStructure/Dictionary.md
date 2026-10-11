# Dictionary<TKey, TValue>
- 자료구조의 일부. 
- 기존 [리스트](List.md)나 [배열](Array.md)이 한번에 하나의 타입만 저장하고 인덱스를 통해 요소를 다룰 수 있었다면 수 있었다면, 딕셔너리는 Key라고 불리는 값이 인덱스 번호를 대신한다. 이렇게 Key와 Value를 세트로 다루는 배열을 연관 배열이며, 딕셔너리는 연관 배열을 다루기 위한 클래스이다.
- Key는 배열, 리스트에서처럼 인덱스 번호, 즉 요소들의 순서를 나타내는 값이므로 중복된 Key는 사용할 수 없다.
- 또한 인덱스 번호가 무조건 숫자로 고정되어 있는 배열, 리스트와 달리, Key 값의 타입을 결정해줄 수 있어 숫자 이외의 문자열을 Key로 사용하는 것도 가능하다.
>Dictionary 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("Hokkaido", "Sapporo");
            myTable.Add("Iwate", "Morioka");
            myTable.Add("Miyagi", "Sendai");
        }
    }
}
```
- 딕셔너리는 Key 값만 취하거나, Value 값만 취하거나, 둘 다 취하는 식으로 다양하게 사용할 수 있다.
>Dictionary Keys 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            foreach(string key in myTable.Keys) 
            {
                Console.WriteLine(key);  
            }
        }
    }
}
```
>Dictionary Values 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            foreach(string value in myTable.Values) 
            {
                Console.WriteLine(value);  
            }
        }
    }
}
```
>Dictionary KeyValuePair 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            foreach(KeyValuePair<string, string> item in myTable) //KeyValuePair는 Keys나 Values처럼 프로퍼티가 아닌 구조체.
            {
                Console.WriteLine(item.Key, item.Value);
            }
        }
    }
}
```
- Key로 Value를 취급하는 방법
    - 상술했듯 Key는 배열, 리스트의 인덱스 번호와 같은 위치이기에 Key 값으로 Value를 찾을 수도 있다.
>Dictionary Key로 Value를 찾는 법 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            string str = "아자차";
            Console.WriteLine(str, myTable[str]);  
        }
    }
}
```
- 요소 검색
    - 요소를 검색하는 방법은 Key, Value 2가지로 나뉘어져 있다.
>Dictionary ContainsKey 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            string str = "아자차";
            if(myTable.ContainsKey(str)) 
            {
                Console.WriteLine($"{str}은 이미 Key로 사용되고 있습니다.");
            } 
            else 
            {
                Console.WriteLine($"{str}은 Key로 사용되지 않고 있습니다.");
            }
        }
    }
}
```
>Dictionary ContainsValue 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Dictionary<string, string> myTable = new Dictionary<string, string>();
            myTable.Add("가나다", "마바사");
            myTable.Add("아자차", "카타파");
            myTable.Add("하하하", "다나까");

            string str = "다나까";
            if(myTable.ContainsValue(str)) 
            {
                Console.WriteLine($"{str}은 이미 Value에 존재하고 있습니다.");
            } 
            else 
            {
                Console.WriteLine($"{str}은 Value에 존재하지 않는 값입니다.");
            }
        }
    }
}
```