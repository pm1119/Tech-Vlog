# Array
- 복수의 데이터를 하나의 변수로 저장하기 위해 사용하는 배열이다.
>Array 사용 예시
```csharp
class Program
{
    static void Main(string[] args)
    {
        class Program
		{
			private static void Main(string[] args)
			{
				int[] arr = new int[5];

				arr[0] = 11;
				arr[1] = 50;
				arr[2] = 20;
				arr[3] = 15;
				arr[4] = 5; //데이터 개수 입력 후 일일이 설정

				for (int i = 0; i < arr.Length; i++)
					Console.WriteLine($"arr[i] = {arr[i]}");

				int[] arr2 = new int[] { 10, 3, 5, 7, 2, 50 }; //배열에 넣을 데이터를 일일이 입력
				for (int i = 0;	i < arr2.Length; i++)
					Console.WriteLine($"arr[i] = {arr2[i]}");
			}
		}
    }
}
```
- [리스트](List.md)와의 비교
    - 공통점
        - 인덱스를 사용하여 요소에 직접 액세스 가능
    - 차이점
		- 리스트는 동적으로 크기가 조정될 수 있음
		- 리스트는 요소의 추가, 삭제, 수정 등이 자유로움
		- 리스트는 제네릭을 통해 타입 안정성이 보장됨
    