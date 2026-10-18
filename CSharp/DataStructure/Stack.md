# Stack
- 자료구조의 일종, [큐](Queue.md)가 통로에 비유된다면 스택은 바구니에 비유된다.
- 담을 수는 있으나 반대편으로 내보낼 수 없는 바구니처럼 들어온 순대로 나가는 큐와 달리 최근에 들어온 값부터 나간다.
- 이것을 후입선출이라 하여 Last In, First Out/LIFO라고 불린다.
>Stack 사용 예시
```csharp
using System;
using System.Collections.Generic;
 
namespace Sample
{
    class Sample
    {
        static void Main()
        {
            Stack stack = new Stack();
            
            stack.Push(1);
            stack.Push(2);
            stack.Push(3); //Push() 메서드를 통해 스택에 값을 넣을 수 있음
            stack.Push(4); //단, 큐와 마찬가지로 중간에 값을 끼워넣는 건 불가능함

            int[] arr = new int[] { 1, 2, 3, 4, 5 };
            Stack anoStack = new Stack(arr); //배열의 값을 스택을 생성할 때 넣어주는 것으로 스택의 값을 초기화할 수 있음

            stack.Peek(); //Peek 메서드를 통해 최상위권의 값을 확인할 수 있음, 데이터는 고정됨

            stack.Pop(); //Pop 메서드를 통해 값을 뺄 수 있음. 
            stack.Pop(); //가장 최근의 값부터 나가므로 남은 값은 2, 1.
            stack.Pop(); //마찬가지로 중간의 값을 제거하는 건 불가능함

            anoQueue.Clear(); //리스트, 큐와 마찬가지로 Clear() 메서드를 통해 모든 값 제거 가능
        }
    }
}
```
- 데이터의 저장이 이루어지는, 웹 브라우저 뒤로 가기, 실행 취소(Ctrl+Z), 함수 호출(Call Stack), 괄호 검사 등에 쓰인다.
- >Stack 사용 예시
```csharp
static void Main()
{
    string[] start = { "{", "[", "(" };
    string[] end = { "}", "]", ")" };

    string test = "{ [ ( ) ( ) ( )  ] }";

    string[] splits = test.Split(' ');

    bool isNullStack = false;
    Stack stack = new Stack();

    for (int i = 0; i < splits.Length; i++)
    {
        if (start.Contains(splits[i]))
        {
            stack.Push(splits[i]);//{ [
        }
        else
        {
            if (stack.Count == 0)
            {
                isNullStack = true;
                break;
            }

            int endindex = Array.FindIndex(end, (item) => item == splits[i]);
            int startindex = Array.FindIndex(start, (item) => item == (string)stack.Peek());

            if (endindex == startindex)
            {
                Console.Write(" " + (string)stack.Pop() + " " + splits[i]);
            }
            else
            {
                stack.Push(splits[i]);
            }
        }
    }//for (int i = 0; i < splits.Length; i++)

    if (stack.Count > 0 || isNullStack)
    {
        Console.WriteLine("수식의 오류");
    }
    else
    {
        Console.WriteLine("정상적인 수식");
    }

    PrintStack(stack);
}

void PrintStack(Stack stack, string desc = "")
{
    Console.WriteLine(desc);
    foreach (var item in stack)
    {
        Console.Write(" " + item);
    }
    Console.WriteLine();
}
```