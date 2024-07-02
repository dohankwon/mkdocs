# 계정에 그룹 권한 주기

```sh
$ sudo usermod -aG <그룹명> <계정명>
```

실행 예:
```sh
$ sudo usermod -aG docker $USER
$ sudo su - $USER
```

## REFERENCE

- [우분투 리늑스 - 계정 생성 및 sudo 권한 주기](https://dalgong2.tistory.com/14)