# HashSet
- using System.Collections.Generic 네임스페이스에 포함된 자료구조 클래스.
- 해시 테이블을 기반으로 만들어졌다.
- 구성 요소
    - 해시 함수
        - 객체의 고유한 해시 코드를 생성하며, 객체의 고유한 상태를 바탕으로 고유한 정수 값을 반환하는 함수.
    - 버킷
        - 양동이를 의미하는 버킷이란 단어처럼, 동일한 해시 코드를 가진 요소들의 목록을 저장한다. 버킷을 배열의 인덱스로 참조된다.
>HashSet 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            HashSet<int> hash = new HashSet<int>();
            
            hash.Add(1);
            hash.Add(2);
            hash.Add(3); 
            hash.Add(4); 

            hash.Add(3); //이 경우는 이미 존재하는 요소이므로 추가되지 않음. 이 경우 false 반환

            hash.Remove(2); //제거할 요소의 해시 코드를 계산하여 해당 버킷을 찾아 요소를 제거. 성공할 시 true, 실패할 시 false 반환

            hash.Contains(2); //특정 요소를 검색할 수 있는 메서드. 해시 코드를 계산하여 해당 버킷을 검사한다. 성공 시 true 반환.

            hash.Clear(); //해시셋의 모든 요소를 제거하는 메서드
        }
    }
}
```