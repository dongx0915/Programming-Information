# Git
<hr>
<br>

## Git 동작 원리
<hr>

<p align="center"><img src = "./Git-image/GIT동작과정.jfif" height = "350px"></img></p>

<b>- Working Directory</b> : 작업할 파일이 있는 디렉토리<br>
<b>- Staging Area</b> : 커밋(Commit)을 수행할 파일들이 올라가는 영역<br>
<b>- Git Directory</b> : Git 프로젝트의 메타 데이터와 데이터 정보가 저장되는 디렉토리<br>

- **원격 저장소(Remote Repository)** 에서 **Clone**을 받으면 컴퓨터에 해당 프로젝트가 통째로 다운로드 됨
- 수정한 내역을 다시 원격 저장소에 반영하려면 **git add**, **git commit**, **git push**의 과정을 거처야 함
- 수정된 내역을 다시 받을 때에는 **git fetch**를 사용(이 과정에서 <u>내가 수정한 내역이 원격 저장소에 있는 내역과 다를 수 있기 때문에</u> **git merge**를 수행)
- **git fetch**와 **git merge**를 한 번에 할 수 있는 **git pull**



# Git 기본 명령어

<hr>

### Git Login
```
- git config --global user.email "useremail@example.com"
- git config --global user.name "username"
```



### Git Clone

 ```
 - cmd -> Clone 받을 폴더로 이동      (change Directory)
 - git clone repository URL          
 ```



### Git status

 ```
 - git status
 ```


### Git add
 - **Staging Area**에 파일을 올리는 작업
 
 ```
  - git add FileName.*       (특정 파일만 add)
  - git add .                (모든 파일을 add)
 ```
 
### Git reset
 - 특정 파일을 **Staging Area**에서 제거
 
```
- git reset FileName.*
```
 
---

### Git commit

```
 - git commit -m "message"
```

### Git push
* **commit** 후 **push**까지 해주어야 **github**에 반영됨
```
 - git push
```

---

### Git checkout 
* 최근 수정 내역을 원상복귀

```
 - git checkout -- FileName.*
```
