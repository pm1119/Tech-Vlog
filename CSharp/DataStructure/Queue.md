# Queue
- 자료구조의 일부로, 통로와도 같은 원리를 가지고 있다.
- 쉽게 설명하면, 들어온 순대로 나가는 것이다. 큐에 1, 2, 3, 4를 집어넣었다고 했을 때, 요소를 뺄 시 들어온 순서대로 먼저 들어온 1이 먼저 빠져나간다.
- 이것을 선입선출이라 하여 First In, First Out/FIFO라고 불린다.
>Queue 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Queue queue = new Queue();
            
            queue.Enqueue(1);
            queue.Enqueue(2);
            queue.Enqueue(3); //Enqueue() 메서드를 통해 큐에 값을 넣을 수 있음
            queue.Enqueue(4); //단, 중간에 값을 끼워넣는 건 불가능함

            int[] arr = new int[] { 1, 2, 3, 4, 5 };
            Queue anoQueue = new Queue(arr); //배열의 값을 큐를 생성할 때 넣어주는 것으로 큐의 값을 초기화할 수 있음

            queue.Peek(); //Peek 메서드를 통해 최상위권의 값을 확인할 수 있음, 데이터는 고정됨

            queue.Dequeue(); //Dequeue()를 2번 사용했을 경우 큐의 기능에 따라 들어온 순서대로 빠지기 때문에 남은 값은 3, 4가 됨
            queue.Dequeue(); //Dequeue() 메서드를 통해 큐의 요소를 제거할 수 있음
            queue.Dequeue(); //마찬가지로 중간의 값을 제거하는 건 불가능함
            queue.Dequeue();

            //queue.Dequeue(); //요소가 모두 제거된 후엔 큐 안에 값이 없으므로 에러가 남

            anoQueue.Clear(); //리스트와 마찬가지로 Clear() 메서드를 통해 모든 값 제거 가능
        }
    }
}
```
- 데이터의 순환이 이루어져야 하는, 프린터 출력 대기열, 은행 번호표 업무, 프로세스 관리 등에 주로 쓰인다.