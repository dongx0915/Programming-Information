## GitHub에 프로젝트 올리기(Windows)
<hr>

#### 1. [Git 설치](https://git-scm.com/downloads)

#### 2. New Repository 생성

#### 3. Repository Url 복사

#### 4. 로컬 컴퓨터에서 업로드하고 싶은 프로젝트 우클릭 > *Git Bash Here*

#### 5. git cmd에서 github 로그인
``` 
  - git config --global user.email "useremail@example.com"
  - git config --global user.name "username" 
```
 
#### 6. .git 파일 생성
``` 
  - git init
```
  
#### 7. 프로젝트 Commit

```
  - git add . (or git add filename.*)
```

```
  - git commit -m "Commit message"
```

#### 8. 프로젝트 업로드

```
  - git remote add origin Repositoy URL
```

```
  - git push -u origin master (origin master 필수)
```

 
 
    
 
