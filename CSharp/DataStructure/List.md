# List
- C#에서 사용하는 자료구조 중 하나. [배열](Array.md)과 함께 가장 많이 사용되는 자료구조로, 동적으로 크기가 조정될 수 있으며 배열처럼 인덱스를 통해 요소 접근이 가능하다.
>List 사용 예시
```csharp
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        class Program
		{
			private static void Main(string[] args)
			{
				List<int> list = new List<int>() { 1, 2, 3 }; //제네릭을 통해 요소의 타입을 미리 정해준다.

				list.Add(4); //Add 메서드를 통해 리스트에 요소를 추가할 수 있다.
				list.Remove(2); //Remove 메서드를 통해 리스트의 요소를 제거할 수 있다.
				list.Clear(); //Clear 메서드를 통해 리스트의 요소를 모두 제거할 수 있다.

				for (int i = 0; i < list.Count; i++) //for 혹은 foreach 루프를 사용해 리스트의 요소를 탐색할 수 있다.
				{
					Console.WriteLine(list[i]);
				}

				foreach (int number in list)
				{
					Console.WriteLine(number);
				}

				list.Sort();
				list.Reverse(); //Sort 메서드로 리스트를 순서대로 정렬할 수 있다. 단, 기본적으로 오름차순으로 정렬하므로 내림차순으로 정렬할 시 Reverse 메서드를 추가 사용한다.

				int num = list.IndexOf(3); //IndexOf 메서드를 사용해 리스트의 요소를 검색할 수 있다. 파라미터로 넣은 요소가 처음으로 나타나는 인덱스를 반환하며, 없을 경우 -1을 반환한다.
			}
		}
    }
}
```
- [배열](Array.md)와의 비교
    - 공통점
        - 인덱스를 사용하여 요소에 직접 액세스 가능
    - 차이점
		- 배열은 요소의 크기가 고정됨
		- 배열의 크기는 생성 시점에 결정되므로 변경 불가능
		- 배열은 다차원 배열을 지원함