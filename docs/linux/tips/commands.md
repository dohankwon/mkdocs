# 명령어/단축키 팁

## 실행 가능한 파일을 찾아서 삭제

- `find` 명령어를 사용해서 실행 가능한 모든 파일을 찾기
```
find . -type f -executable
```

- 현재 디렉토리에서만 검색하는 것으로 제한해서 찾기
```
find . -maxdepth 1 -type f -executable
```

- 현재 디렉토리에 있는 실행 가능한 모든 파일을 찾아서 삭제하기
```
find . -maxdepth 1 -type f -executable -exec rm {} +
```

- As a side note, if you want to find files executable by any user, not just the current user (set as regular execute permission bits):
```
find . -type f -perm /111
```
```
find . -type f -perm +0111
```

- `.git` 디렉토리를 제외한 나머지 디렉토리의 실행 가능한 모든 파일 삭제하기
```
find . -not -iwholename '*.git*' -type f -executable - exec rm {} +
```

## tar, gz 압축 및 해제

- tar -cvf [파일명.tar] [폴더명]
```
tar -cvf xyz.tar abc
```

- tar -xvf [파일명.tar]
```
tar -xvf xyz.tar
```

- tar -zcvf [파일명.tar.gz] [폴더명]
```
tar -zcvf xyz.tar.gz abc
```

- tar -zxvf [파일명.tar.gz]
```
tar -zxvf xyz.tar.gz
```

## 홈/마지막 작업 디렉토리로 이동

- 홈 디렉토리로 이동하기
```
cd ~
```

- 현재 디렉토리로 이동하기 바로 직전 디렉토리로 이동하기
```
cd -
```

## Command 줄의 처음/끝으로 이동

- Command 명령줄에 입력된 내용의 처음으로 이동하기 단축키 : `Ctrl + A`
- Command 명령줄에 입력된 내용의 마지막으로 이동하기 단축키 : `Ctrl + E`

## 커서 위치에서 앞/뒤 내용 삭제

- 커서 위치에서 앞(왼쪽) 내용 삭제하기 단축키 : `Ctrl + U`
- 커서 위치에서 뒤(오른쪽) 내용 삭제하기 단축키 : `Ctrl + K`

## REFERENCE

- [시간을 절약하는 리눅스 명령어 TIP 모음](https://inpa.tistory.com/entry/LINUX-%F0%9F%93%9A-%EC%8B%9C%EA%B0%84%EC%9D%84-%EC%A0%88%EC%95%BD%ED%95%98%EB%8A%94-%ED%84%B0%EB%AF%B8%EB%84%90-%EB%8B%A8%EC%B6%95%ED%82%A4-Command-Line-Tip)
