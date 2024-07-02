# Windows 탐색기 Context Menu에서 새로 만든 Text Document(*.txt)의 기본 문자열 넣기

요즘 하는 업무로 Windows 탐색기의 Context Menu에서 Text Document 새로 만들기를 많이 하고 있다.
같은 일을 반복해서 많이 하다보니 새로 만든 TXT 파일에 의미없는 내용을 입력하는 작업이라도 줄여보고자 레지스트리(registry)를 뒤져봤다.

Windows 탐색기를 실행하고, 마우스 오른쪽 버튼을 누르면 나오는 Context Menu에서 "새로 만들기 > Text Document" 메뉴를 선택하면 "새 텍스트 문서.txt" 파일이 만들어지는데, 이 파일은 기본적으로 아무런 값도 가지고 있지 않은 널 파일(Null File)이다.

새로 생성되는 TXT 파일에 내가 지정한 문자열을 자동으로 갖도록 하기 위해서는 아래 레지스트리 편집을 하면 가능하다.

`HKEY_CLASS_ROOT\.txt\ShellNew` 키에 Data 문자열 값 "TEST FILE"을 추가한다.

이제부터는 새로 만드는 Text Document가 Null 파일이 아니라, 내가 지정한 값을 가지고 있는 파일로 생성되는 것을 확인할 수 있다.[text](vscode-local:/c%3A/Workspaces/github/mkdocs/docs/windows/assets)