# Github에 있는 파일 또는 폴더 삭제하기

> 파일 삭제하기, 폴더 삭제하기 모두 터미널 창 또는 cmd를 켠 뒤 삭제하고자하는 파일/폴더가 있는 위치로 이동해서 실행

> 삭제한 후에는 commit 및 push

# 파일  삭제하기
## 1. 로컬 디렉토리와 git 저장소에서 모두 삭제
```
$ git rm HelloWorld.java
$ git commit -m "Delete HelloWorld.java"
```
파일을 삭제한 후 commit & push를 꼭 해줘야함


## 2. 로컬 디렉토리에서는 삭제하지 않고 git에서만 삭제
실수로 .class 같은 커밋하지 말아야 할 파일들을 커밋하는 경우가 있다.
이런 경우 다음 명령어를 사용하면 로컬 디렉토리의 파일은 유지한 채 git에서만 삭제할 수 있다.

```
$ git rm --cached HelloJAVA.class
$ git commit -m "Delete HelloJAVA.class"
```

# 폴더 삭제하기
## 1. 로컬 디렉토리와 git 저장소에서 모두 삭제
```
$ git rm -rf 폴더명
$ git commit -m "delete folder"
```

## 2. 로컬 디렉토리의 폴더는 유지한 채 git 저장소에서만 폴더 삭제하기

이클립스와 git을 연동하여 commit & push 하던 중 bin 폴더와 src 폴더를 모두 commit & push를 해서 bin 폴더는 git 저장소에서 삭제하고자 한다.

```
$ git rm --cached -r bin/
$ git commit -m "delete folder"
```
