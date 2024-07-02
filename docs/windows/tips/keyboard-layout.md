# Shift + Space 키로 한/영 전환

하안글 워드프로세스를 많이 사용했던 사람이라면 한/영 전환을 위해서 Shift + Space 키를 한/영 전환을 위해서 많이 사용했을 것 같다.
나 역시 마찬가지다.

혹시라도 Windows를 설치하다가 3번째 타입의 키보드를 선택하지 않았다면 키보드 상의 한/영 전환키를 이용해서 사용해야 할 것이다.
무엇보다도 익숙하지 않기 때문일테지만 나는 이것이 상당히 귀찮다고 느낀다.
그래서 이미 설치되어있는 Windows 시스템에서는 한/영 전환키를 Shift + Space 키로 바꾸는 일을 꼭 한다.

방법은 레지스트리 편집기를 통해서 할 수 있다.

`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\i8042prt\Parameters` 키에 보면, `LayerDriver KOR` 문자열에 `kdb101c.dll` 로 수정한 다음 시스템을 재부팅하면 끝이다.
