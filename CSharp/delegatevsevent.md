# delegate vs event
- [delegate](delegate.md)
    - 하나의 형식으로, 메서드에 대한 참조이다. 값이 아닌 코드 자체를 넘기고 싶을 때, 즉 콜백 용도로 사용한다.
    - 인터페이스 내부에서 선언 불가능하다.
- [event](event.md)
    - delegate에 event를 수식하여 선언한 것.
    - 객체의 상태 변화와 사건의 발생 여부를 알리기 위해 사용한다.
    - 인터페이스 내부에 선언할 수 있다.