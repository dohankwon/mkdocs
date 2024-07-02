# Windows 탐색기 Context 메뉴를 통한 명령 프롬프트 실행하기

Windows 탐색기를 사용하다가 현재 폴더에 명령 프롬프트를 실행해야 하는 경우가 종종 있다.
이 때, Window + R(실행)을 누르고, cmd 명령을 입력해서 명령 프롬프트를 띄운 다음 현재 폴더로 변경하는 일련의 작업은 상당히 귀찮다.

이러한 일련의 작업을 레지스트리에 등록해놓으면 Windows 탐색기의 Context 메뉴를 통해 편하게 명령 프롬프트를 실행할 수 있다.
변경해야 하는 레지스트리 값은 아래와 같다.

1. `HKEY_CLASSES_ROOT\Directory\shell\cmdprompt` 키 추가
    - (기본값) REG_SZ `명령 프롬프트 실행`
    - Icon REG_SZ `cmd.exe, 1`
1. `HKEY_CLASSES_ROOT\Directory\shell\cmdprompt\command` 키 추가
    - (기본값) REG_SZ `cmd.exe /s /k pushd "%V"`
1. `HKEY_CLASSES_ROOT\Directory\Background\shell\cmdprompt` 키 추가
    - (기본값) REG_SZ `명령 프롬프트 실행`
    - Icon REG_SZ `cmd.exe, 1`
1. `HKEY_CLASSES_ROOT\Directory\Background\shell\cmdprompt\command` 키 추가
    - (기본값) REG_SZ `cmd.exe /s /k pushd "%V"`

레지스트리 편집기에서 정상적으로 값들을 모두 입력하였다면 Windows 탐색기에서 팝업메뉴로 "명령 프론프트 실행"라는 항목이 추가되었음을 확인할 수 있다. 
아울러, 아이콘도 표시되어 눈으로 찾기가 쉽다.

## PowerShell 실행하기

파워쉘^PowerShell^도 명령 프롬프트와 마찬가지로 Context 메뉴에 추가할 수 있는데, 이 때 등록할 명령^command^ 키는 아래와 같다.

```
powershell.exe -noexit -command "Set-Location -LiteralPath '%V'"
```

## `.reg` 파일

레지스트리 열어서 편집하기 귀찮아서 그냥 파일을 하나 첨부했다.
첨부된 파일을 다운로드하고 기존 레지스트리에 병합하면 OK~!

- [명령 프롬프트](assets/ExplorerPrompt.reg)
- [PowerShell](assets/ExplorerPowerShell.reg)
