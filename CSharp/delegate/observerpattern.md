# Observer Pattern
- delegate와 event를 사용해 구사할 수 있는 코드 기법으로, 주체(subject) 객체에 의존하는 옵저버(observer) 객체들이 있다고 했을 때 주체의 상태에 변화가 생겼을 때 옵저버들에게 알림을 보내 효율적으로 상태 변화를 수행할 수 있는 패턴이다.
- 게임에선 주로 체력 변화 등 런타임 데이터 관리에 주로 사용된다.
>Observer Pattern 예시
```csharp
public class Hero //플레이어 클래스(주체)
{
    float maxHp;
    float currentHp;

    public event UnityAction<float, float> OnHpChanged;

    public void TakeDamage(float damage)
    {
        currentHp = Mathf.Min(currentHp -  damage, maxHp);   
        OnHpChanged?.Invoke(currentHp, maxHp); //이벤트 발행을 통해 상태 변화 알림
    }
}

public class PlayerView //체력 바 클래스(옵저버)
{
    Image _hpBar;

    public void HpChangeView(float currentHp, float maxHp) //이벤트를 구독할 함수
    {
        _hpBar.fillAmount = currentHp / maxHp;
    }
}

public class PlayScene //주체의 알림과 객체의 처리를 담당하는 클래스
{
    Hero hero;
    PlayerView playerView;

    private void Awake()
    {
        boss.OnBossHpChanged += bossView.HpChangeView;
    }
}
```