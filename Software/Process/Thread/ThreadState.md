# Thread State
![ThreadState.](https://laboputer.github.io/assets/img/csharp/11-1.png)
- 스레드가 생성되어 종료될 때까지 거치는 생명주기(Lifecycle).
- 상태 목록
    - UnStarted
        - 스레드 객체를 생성한 후 Thread.Start() 메소드가 호출 되기 전의 상태.
    - Running
        - 스레드가 시작하여 동작 중인 상태. Unstarted 상태의 스레드를 Thread.Start() 메소드를 통해 이 상태로 만들 수 있음.
    - Suspended
        - 스레드의 일시 중단 상태. 스레드를 Thread.Suspend() 메소드를 통해 이 상태로 만들 수 있으며, Suspended 상태인 스레드는 Thread.Resume() 메소드를 통해 다시 Running 상태로 만들 수 있음.
    - WaitSleepJoin
        - 스레드가 블록(Block)된 상태. 스레드에 대해 Monitor.Enter(), Thread.Sleep(), Thread.Join() 메소드를 호출하면 이 상태로 변환됨.
    - Aborted
        - 스레드가 취소된 상태. Thread.Abort() 메소드를 호출하면 이 상태로 변환됨. Aborted 상태가 된 스레드는 다시 Stopped 상태로 전환되어 완전히 중지됨.
    - Stopped
        - 중지된 스레드의 상태. Thread.Abort() 메소드를 호출하거나 스레드가 실행 중인 메소드가 종료되면 이 상태로 변환됨.
    - Background
        - 스레드가 백그라운드로 동작되고 있음을 나타내는 상태. Foreground 스레드는 하나라도 살아있는 한 프로세스가 죽지 않지만, Background는 여러 개가 살아 있어도 프로세스가 죽고 사는 것에는 영향을 미치지 않음. 하지만 프로세스가 죽으면 Background 스레드는 모두 죽음. Thread.IsBackground 속성에 true 값을 입력하면 스레드를 이 상태로 바꿀 수 있음.